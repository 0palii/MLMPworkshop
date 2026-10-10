**Project**

Repository: https://github.com/facebookresearch/segment-anything.git

Inference task: Object detection

**Repo map**

Environment: pyproject.toml

Entry point: amg.py

Model: sam_vit_h_4b8939.pth

Input: /home/<your location>/segment-anything/assets/<your input>
Output: /home/<your location>/segment-anything/<your output>

**Environment setup**
```text
git clone https://github.com/facebookresearch/segment-anything.git
cd /<your location>/segment-anything
uv venv --python 3.13.14
source .venv/bin/activate
uv pip install torch torchvision
uv pip install opencv-python pycocotools matplotlib onnxruntime onnx jupyter
uv pip install -e .
mkdir -p checkpoints
# place <your model>.pth in checkpoints/
wget <URL of the model, eg:sam_vit_h_4b8939.pth>
# ensure <your input> exists and is readable
mkdir -p output
# this will be where you put your output
```

**Inference** 
```text
python scripts/amg.py --checkpoint /home/<your location>/segment-anything/checkpoints/sam_vit_h_4b8939.pth --model-type vit_h --input /home/<your location>/segment-anything/assets/<your input> --output /home/<your location>/segment-anything/output
```

**One real failure**

Category: FileNotFoundError

Root cause: My checkpoint and the sample picture are not placed in the right directory, so i have to make a directory called "chekpoints" and put the picture in the directory called "assets".

Minimal fix: put the checkpoint and the picture in the right place.

**AI agent check**

Which AI coding agent did you use?: copilot

What did it change?: wrote me a test file that did not really worked out.

How did you verify the change?: I asked it to do this and then discovered that i did not really need this, because there is a sample of amg.py.
