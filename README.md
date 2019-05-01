# hand-gesture-controlled-vlc-player-tensorflow-object-detection-api
control a vlc player using hand gesture using tensorflow object detection api  model trained using colab

capture the images from webcam with a l and i gesture images of 250 using the program

## label the image data using 
https://github.com/tzutalin/labelImg

take 70% images of al and i to train directory and 30 % to test directory

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

you bata-colab directory will look like this   

data-colab/  
-data/  
-images.zip  
-training/  
--object-detection.pbtxt    
--ssd_mobilenet_v1_pets.config  
-xml_to_csv.py  
-protobuf.zip  
-generate_tfrecord.py  

open the object-detection.ipynb program and run the program using colab  
https://colab.research.google.com/  

after running the program you will get a trained model in  

hand_sign_out_inference_graph directory   
downlod the directory into your local pc   
run the object_detection_webcam_1.py  
