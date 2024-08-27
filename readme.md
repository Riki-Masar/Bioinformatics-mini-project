Bioinformatics mini project:
This project aims to find 2 key points in bacteria images, a point on each edge of the bacterium.
I used google colab notebooks, python language.
I started by writing a basic CNN model which I trained on 500 circles which I generated.
The model aimed to find the circle's centre point which it did. I used mobileNetV2 pretrained model and added some layers.
Over all i'm quite pleased with the circles notebook because it works pretty well and that all I needed before I continued forth with the bacteria images.

After completing the circles model, I started working on the bacteria images. The bacteria images were given to me by Dr Moshe Amitai, they are images of same bacteria under two different conditions: 1. Acidic 2.Alkeline
I started by drawing two edge points on each bacterium using VGG aplication which at the end resulted with a CSV file of all the points. I then dowloaded them into my drive and accesed both the images and CSV file from colab.
A problem that aroused was that the images were all in different sizes. 
To fix the sizes problem, I completed the images with black background so each image becomes 224*224. (The model needs all images to be of the same size when training)
I used MSE as a loss function because my problem is regression. The input were bacteria images, the output is 4 neurons - X & Y coordinates for 2 points.
I then trained 10 images and recieved MSE value of 0.03 which is great. (The closer the MSE values are closer to 0, the better)
Ithen visualised the predictions on 10 test images to see that my model actually works quite well but isn't prefect. 
I can still improve the model maybe by playing with the hyper parameters but this is the best results I managed to get for now.

I then carried on by trying my model on 300 images. I split the images to 0.8 training and 0.1 validation & 0.1 test.
In this model I changed the activation function from RELU to Leaky RELU and it did im-prove slightly.
Here the MSE results were in the 40's which is higher but still quite good. When visualising the predictions on the test images, the results were not bad for most of the images.
Also for this notebook, I can probbably improve the performance of the model, but I did try other pre trained model and mobileNetV2 worked best.

Overall, I used MobileNetV2 pretrained model, ADAM optimiser, dropout of 0.2 and augmentation.
