# RockPaperScisssorsProject
Rock Paper Scissors Game Detector

This project uses NVIDIA's Jetson Nano Bot and a dataset from Kaggle to detect and classify hand gestures into one of three categories: rock, paper, or scissors. The dataset I used for this project is available on Kaggle and contains images of hands forming rock, paper, and scissors signs. We have used the pre-trained ResNet-18 model from ImageNet to classify these images into the respective categories.

Before starting, ensure you have the following software installed: 

- NVIDIA Jetson Nano Bot
- Python 3.6 or later
- CUDA toolkit
- PyTorch

https://imgur.com/ZBGReib

1. Set up the nvdia nano bot
2. Connect the nano to your pc using putty (select SSH mode, you will need the ip adress)
3. Log in into the Linux Terminal using username: Nvidia and password: Nvidia
4. Download the jetson-inference folder, the machine learning and the model will run inside this folder
5. Open VSC on the PC and connect the nano
6. Go to the nvidia folder
7. Open up a new terminal with the task bar  
8. Go inside the jetson-inference folder using cd jetson-inference/
9. Now the docker command will be used to enter the docker container  [./docker/run.sh]
10. Download the BRock model which can be found in the repository
11. Enter cd python/training/classification and export the model [python3 onnx_export.py --model-dir=models/BRock]
12. Run [NET=models/BRock] and [DATASET=data/BRock] to set the dataset variables
13. Use this command to feed images into the model from the testing set imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/rock/testrock01-10.png
14. 
