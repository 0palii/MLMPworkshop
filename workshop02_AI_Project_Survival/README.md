**Project**

Repository: https://github.com/facebookresearch/segment-anything.git

Inference task: Object detection

**Repo map**

Environment: pyproject.toml & requirements.txt

Entry point: detect.py

Model: The detect.py automatically downloads models from the latest YOLOv5 release 

Input: /home/s5908294/workshop02_project/segment-anything/assets/alien.jpg
Output: /home/s5908294/workshop02_project/segment-anything/output/0-19.png

**Environment setup**
```text
git clone https://github.com/facebookresearch/segment-anything.git
cd /home/s5908294/workshop02_project/segment-anything
uv python install 3.13.14
uv venv --python 3.13.14
source .venv/bin/activate
uv pip install torch torchvision
uv pip install opencv-python pycocotools matplotlib onnxruntime onnx jupyter
uv pip install -e .
```

**Inference** 
```text
python scripts/amg.py \
  --checkpoint /home/s5908294/workshop02_project/segment-anything/checkpoints/sam_vit_h_4b8939.pth \
  --model-type vit_h \
  --input /home/s5908294/workshop02_project/segment-anything/assets/alien.jpg \
  --output /home/s5908294/workshop02_project/segment-anything/output
```

**One real failure**

Category: FileNotFoundError

Root cause: My checkpoint and the sample picture are not placed in the corresponding directory, so i have to make a directory called "chekpoints" and put the picture in the directory called "assets".

Minimal fix: put the checkpoint and the picture in the right place.

**AI agent check**

Which AI coding agent did you use?: copilot

What did it change?: wrote me a test file that did not really worked out.

How did you verify the change?: I asked it to do this and then discovered that i did not really need this
