# Dataset

&nbsp;

This folder is a template that you can use as a reference. Different task (classification, segmentation ecc..) need data in different format.
Just choose the right one and put your data following the below schema.

DO NOT ADD THE CONTENT OF DATASET FOLDER TO GIT


&nbsp;

# How to Use

&nbsp;

Create a **Data/Dataset** folder and follow one of the Data Task below based on what you have to do.


For example if you need to train a Classification Model put your data ad described in "Data for Classification Model" Section below

&nbsp;

# Data for Anomaly Detection Model

&nbsp;

## Train Dataset

&nbsp;

    /train
        /good
            /img1.png .jpg


In the train dataset you need only to put images of good. No defect

&nbsp;

## Test Dataset

&nbsp;

    /test
        /good
            /img_good1.png .jpg
        /defect1
            /img_defect1.png .jpg
        /defect2
            /img_defect2.png .jpg

In the test dataset you can test how the model performs. For example you can add images of defects following the above format.

&nbsp;

## Predict Dataset

&nbsp;

COOMING SOON

&nbsp;

# Data for Classification Model

&nbsp;

To train a classification model and have data versioning, you need to put data in the following format

&nbsp;

## Train Dataset

&nbsp;

    Dataset/train

        cls1/
            img1.jpg
        cls2/
            img1.jpg
        clsN/
            img1.jpg

this folder is used to train your model. By default classification use kfold cross validation with split 5. This means  80% train e 20% validation

&nbsp;

## Test Dataset

&nbsp;

    Dataset/test

        cls1/
            img1.jpg
        cls2/
            img1.jpg
        clsN/
            img1.jpg

This folder is used to verify model performance for test dataset. This dataset have to be annotated, so have this folder structure.

Usually you can use test dataset on data taken from production and build your model on a different dataset. Sometimes you need to keep test Dataset fixed while train dataset can change.

&nbsp;

## Predict Dataset

&nbsp;

    Dataset/predict/
        img1.jpg
        img2.jpg
        imgN.jpg

This folder is used to classify images without label. For example if you want to use a previous model to augment your train dataset you can run predict.py on this folder.

The output will be 

    /predict/
        cls1/
            img1.jpg
        cls2/
            img1.jpg
        clsN/
            img1.jpg

You can add this folder to your dataset/train to use model prediction to augment your dataset. 


&nbsp;

# Data for Object Detecion Model

&nbsp;

To train a Object Detecion model and have data versioning, you need to put data in the following format

&nbsp;

## Train Dataset

&nbsp;

    Dataset/train

        images/
            img1.jpg
        annotations/
            instance_default.json COCO Format
        


Annotations have to be in **COCO Format**

&nbsp;

## Test Dataset

&nbsp;

    Dataset/test

        images/
            img1.jpg
        annotations/
            instance_default.json COCO Format

This folder is used to verify model performance for test dataset. This dataset have to be annotated, so have this folder structure.

Usually you can use test dataset on data taken from production and build your model on a different dataset. Sometimes you need to keep test Dataset fixed while train dataset can change.

&nbsp;

## Predict Dataset

&nbsp;

    Dataset/predict

        images/
            img1.jpg

This folder is used to obtain object detection label in COCO format using model. For example if you want to use a previous model to augment your train dataset you can run predict.py on this folder.

The output will be 

   Dataset/predict

        images/
            img1.jpg
        annotations/
            instance_default.json COCO Format

You can add this folder to your dataset/train to use model prediction to augment your dataset. 


&nbsp;

# Data for Segmentation Model

&nbsp;

To train a segmentation model and have data versioning, you need to put data in the following format

&nbsp;

## Train Dataset

&nbsp;

    Dataset/train

        images/
            img1.jpg
        mask/
            img1.png
    
    Dataset/val

        images/
            img1.jpg
        mask/
            img1.png
        
train and val folders are used to train the model and verify accuracy.
Note mask need to be in png and binary format

**To see an example have a look inside example_data/segmentation**

&nbsp;

## Test Dataset

&nbsp;

    Dataset/test

        images/
            img1.jpg
        mask/
            img1.png

This folder is used to verify model performance for test dataset. This dataset have to be annotated, so have this folder structure.

Usually you can use test dataset on data taken from production and build your model on a different dataset. Sometimes you need to keep test Dataset fixed while train dataset can change.

&nbsp;

## Predict Dataset

&nbsp;

    Dataset/predict

        images/
            img1.jpg
    

This folder is used to run segmentation model on images without label. For example if you want to use a previous model to augment your train dataset you can run predict.py on this folder.

The output will be 

    Dataset/predict

        images/
            img1.jpg
        mask/
            img1.png


**Inside mask folder there are predicted masks of images inside images folder.**



