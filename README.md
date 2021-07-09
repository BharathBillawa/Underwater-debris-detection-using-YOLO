
# Underwater debris detection using YOLO v4

This is an example of under debris detection from footage captured by remotely operated underwater vehicles (ROVs). From the standpoint of easier deployment for realtime operations, the project employs the YOLO v4 model.

## Dataset
The dataset used in the project is from **TrashCan:** *A Semantically-Segmented Dataset towards Visual Detection of Marine Debris* . In addition, the dataset includes suggested sets of training and validation samples drawn from a total of 7212 images. This set contains 6065 training images and 1147 validation images. These suggestions are used to evaluate the model's performance.

## How to run the model?
In the darknet detector, use the following configuration and data files:

>  - yolov4_custom_test.cfg
>  - classes.names
>  - yolov4.data

### Examples:
#### For Images

    ./darknet detector test data/yolov4.data cfg/yolov4_custom_test.cfg yolov4_custom_train_best.weights {img_path} -dont_show
Replace `{img_path}` with the actual path to the image to be tested. Model will output the results as `prediction.jpg`, which can be changes by specifying the output file name/ location.

![yolo_detect8](https://user-images.githubusercontent.com/11042326/125073609-85e84f80-e0bc-11eb-845d-cf3e8e3fcb77.png =250x) ![yolo_detect1](https://user-images.githubusercontent.com/11042326/125073813-cf389f00-e0bc-11eb-8f4d-b57c77efee99.png =333x)
#### For videos

    ./darknet detector demo data/yolov4.data cfg/yolov4_custom_test.cfg backup/yolov4_custom_train_best.weights {vid_path} -out_filename {output_path} -dont_show -map
Replace `{vid_path}` and `{output_path}` with actual paths to real source and expected output.

## Performace
Model achieved a best mean Average Precision (_mAP_) of 87% for 8000 iteration of model training.

![Mediamodifier-Design-Template](https://user-images.githubusercontent.com/11042326/125074706-ea57de80-e0bd-11eb-820a-593e24dfa01f.png)

## References

 1. Hong, Jungseok, Michael Fulton, and Junaed Sattar. *"TrashCan: A Semantically-Segmented Dataset towards Visual Detection of Marine Debris."* _arXiv preprint arXiv:2007.08097_ (2020). https://arxiv.org/abs/2007.08097 
 2. Image annotation tool used: https://www.makesense.ai/
