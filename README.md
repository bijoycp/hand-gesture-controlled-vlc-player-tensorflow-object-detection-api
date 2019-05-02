# hand-gesture-controlled-vlc-player-tensorflow-object-detection-api
control a vlc player using hand gesture - tensorflow object detection api  model trained using colab

capture the images from webcam with a, l and i gesture images of 250 using the program

## label the image data using 
https://github.com/tzutalin/labelImg

take 70% images of al and i to train directory and 30 % to test directory

## upload to google drive
upload the images and the data files to google drive name data-colab

uplod generate_tfrecord.py file  
https://github.com/datitran/raccoon_dataset/blob/master/generate_tfrecord.py  
downlod   
wget https://raw.githubusercontent.com/tensorflow/models/master/object_detection/samples/configs/ssd_mobilenet_v1_pets.config  

edit -> ssd_mobilenet_v1_pets.config  

model {  
  ssd {  
    num_classes: 1    ----- your classnumber here i use 5 labels so "num_classes: 5"  
    box_coder {  
      faster_rcnn_box_coder {  
        y_scale: 10.0  
        
uplod  data-colab/training/  

create file object-detection.pbtxt   
object-detection.pbtxt  

item {  
  id: 1  
  name: 'A'  
}  
item {  
  id: 2  
  name: 'B'  
}  
item {  
  id: 3  
  name: 'I'  
}  
item {  
  id: 4  
  name: 'L'  
}  
item {  
  id: 5  
  name: 'V'  

save   
upload to data-colab/training/  

your bata-colab directory will look like this   

data-colab/  
-data/  
-images.zip  
-training/  
--object-detection.pbtxt    
--ssd_mobilenet_v1_pets.config  
-xml_to_csv.py  
-protobuf.zip  
-generate_tfrecord.py  

## run the program in colab
open the object-detection.ipynb program and run the program using colab  
https://colab.research.google.com/  

## download the trained model
after running the program you will get a trained model in  

hand_sign_out_inference_graph directory   
downlod the directory into your local pc 
## runthe program in pc 
your object-detection directory will look like this 
object-detection/  
-utils/  
-- ......  
-protos/  
--....  
-hand_sign_out_inference_graph/  
--frozen_inference_graph.pb  
--model.ckpt.data-00000-of-00001  
--model.ckpt.index  
--model.ckpt.meta  
--....  
-object_detection_webcam_1.py  

run the object_detection_webcam_1.py python program  


![output](https://user-images.githubusercontent.com/18006433/57104114-2a381400-6d45-11e9-982d-01925266f207.png)
