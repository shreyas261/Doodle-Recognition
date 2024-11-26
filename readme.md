# Doodle Recognition
"Quick, Draw!" was released as an experimental game to educate the public in a playful way about how AI works. The game prompts users to draw an image depicting a certain category, such as ”banana,” “table,” etc. Our objective is to recognise hand drawn doodles.

## Contributors
24M0750 : Ritesh Bhadane
24M0757 : Puneet Garg
24M0776 : Shreyas Namjoshi

## How to run code
Install dependencies:
```
pip install -r requirements.txt
```

## Doodle Dataset location:
Click on the **Download all** button after signing up on Kaggle
```
https://www.kaggle.com/competitions/quickdraw-doodle-recognition/data
```

## Modifications in file path
In all the files, modify the variable **path** with path of training dataset followed by two forward slashes i.e *//*. And replace test path to your testing dataset path.

## Run
Run the notebooks named *trainCNN.ipynb*, *trainResnet18.ipynb*, *trainResnext101.ipynb*, *trainReset50.ipynb*  
You can set your parameters and number of classes via :  
Setting the argument nrows of dataset class and num_classes variable.

You can test your model on test dataset using given test snippet for per epoch:
```
for images,labels in testdataloader:
    outputs = model(images.to(device))
    _,output = torch.max(outputs,1)
    a += (output == labels.to(device)).sum().item()
    i += batch_size
```

## Additional results
Models Resnext101 and Resnet50 didn't training completely because of unavailability of compute. Referencing from kaggle competition we can imply that Resnext101 gives 94.6% testing accuracy if trained on complete dataset and all classes. A small confusion matrix for 5 doodles on misclassification for CNN model is given below:

| Actual \ Predicted | Airplane | Tree | Banana | Hand | Fish |
|--------------------|----------|------|--------|------|------|
| **Airplane**       | 68       | 8    | 11     | 5    | 8    |
| **Tree**           | 8        | 70   | 8      | 6    | 8    |
| **Banana**         | 11       | 8    | 65     | 8    | 8    |
| **Hand**           | 5        | 6    | 8      | 74   | 7    |
| **Fish**           | 8        | 8    | 8      | 7    | 69   |

## Logs of models
Screenshots of logs for different models are:
* sad
* adas


