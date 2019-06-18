# Face Recognition with HOG and dlib
## https://medium.com/@patrickhk/face-recognition-with-opencv-without-deep-learning-435cb6d36a53

We can use the pre-trained HOG face_detector by dlib OR CNN face detector to capture the facial part. Using CNN face detector is slower but have higher accuracy. Lets see the difference.
![1](https://cdn-images-1.medium.com/max/600/1*Ro_dmf_8MAmOpywbCUKMvQ.png)<br/>
Wolverine Huge Jackman’s face turns sideway therefore harder to detect.<br/>
![2](https://cdn-images-1.medium.com/max/800/1*zepHAddipdWOp6_27Og0dw.png)
![3](https://cdn-images-1.medium.com/max/800/1*5zLX22bKh_0PrjVoPNJ-AQ.png)<br/>
After capturing the face we usually identify the face landmark, such as eyes, mouth,jaw,nose..etc. It is common to use iBUG 300-W dataset to identify 68 facial landmark points. You can use HELEN dataset to try with 194 points.<br/>
![4](https://cdn-images-1.medium.com/max/800/1*zks0QVydEbFLUxCPLNtaOw.png)<br/>
Apply facial landmark is for doing some transformation to make important features, such as eyes and mouth become the center of the image for easier detection.<br/>
![5](https://cdn-images-1.medium.com/max/800/1*77RYBqg1Jr-bEt-mTcYNOw.png)<br/>
Then we will do some encoding to turn the above facial image part into np array then to embedding vector. This gives us many flexibility to analyze and do the prediction. You can consider increase the embedding dimension to better capture the representation of data. Default in dlib is 128.<br/>
![6](https://cdn-images-1.medium.com/max/800/1*UCBGf-_xIIZpZaXFFRW7GA.png)<br/>
If you have one embedding vector for James Franco, one for Ezra Miller. Then you turn your testing image into embedding vector and compare with that of James Franco and Ezra Miller, you will know who is the person on the photo. Similar concept you can pass multiple batch of images from different people to train a classifier. Since I’m reading the source codes of face_recognition by Ageitgey , therefore I follow him to use K-NN. You can try SVM or other ML algo and compare the accuracy.<br/>
![7](https://cdn-images-1.medium.com/max/800/1*Bv6NUUzo81606e5rzbrdKg.png)<br/>

By using the same bad quality webcam, this time the face recognizer can correctly recognize James Franco. Lets see the a challenging one.<br/>
![22](https://cdn-images-1.medium.com/max/800/1*D9LsQIDpJytdpmkFtfDq4w.jpeg)
![23](https://cdn-images-1.medium.com/max/800/1*iXQ80Kw_7o8ts3eXwdlozQ.png)<br/>

Actually I am very surprised it can distinguish James Franco and Ethan Hawke, provided that my webcam is so blurred. I am very satisfied about the accuracy of HOG, dlib and face_recognition. However the speed is not good enough therefore applying through webcam will be a bit lag.

-------------------------------------------------------------------------------------------------------------------------------------
### More about me
[[:pencil:My Medium]](https://medium.com/@patrickhk)<br/>
[[:house_with_garden:My Website]](https://www.fiyeroleung.com/)<br/>
[[:space_invader:	My Github]](https://github.com/fiyero)<br/>
