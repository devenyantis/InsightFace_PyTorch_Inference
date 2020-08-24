## InsightFace PyTorch Inference
Taken from [InsightFace_PyTorch](https://github.com/TreB1eN/InsightFace_Pytorch). More explanation and references can be referred to the original repo.

The purpose of this repo is to fix and modify the inferencing section of the original repo.

__Tested on Ubuntu 18.04__

## How to use

### Environment setup
1. Clone the repo
2. Download pretrained_model from original repo. Tested with IR-SE50 model
- [Download model](https://onedrive.live.com/?authkey=%21AOw5TZL8cWlj10I&cid=CEC0E1F8F0542A13&id=CEC0E1F8F0542A13%21835&parId=root&action=locate)

3. Place downloaded model in the ```work_space/save/``` directory and rename to ```model_cpu_final.pth``` for cpu machine.
4. Install all dependencies from requirements.txt
- Setup virtual environment ```virtualenv env -p python3```
- ```pip install -r requirements.txt```

### Prepare data
All face data (images, embeddings, etc) are stored in the ```facebank/``` directory. You will need to make the directory in ```data/``` 

Then, prepare the face you want to detect. There are 2 preparation methods.

1. Use pre-existing face images by placing them into the directory
```
data/facebank/
            name1/
                photo1.jpg
                photo2.jpg
                ...
            name2/
                photo1.jpg
                photo2.jpg
```

2. Use webcam to capture new images
```
python take_pic.py -n name
press 't' to capture and 'q' to exit
```
This will create a directory called ```name``` in ```data/facebank```. All captured faces are stored inside it.

### Test model
```python face_verify.py```

To update facebank, use ```-u``` flag

```python face_verify.py -u```

Press 'q' to exit.
