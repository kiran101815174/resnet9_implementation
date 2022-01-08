# resnet9_implementation

This notebook is resnet9 implementation for the dataset
https://www.kaggle.com/crowww/a-large-scale-fish-dataset 
from kaggle

There are a total of 9 category fishes
1) Black Sea Sprat
2) Gilt Head Bream
3) Horse Mackerel
4) Red Mullet
5) Red Sea Bream
6) Sea Bass
7) Shrimp
8) Striped Red Mullet
9) Trout
Each class 1000 images


Resnet9 Architecture
![](http://raw.githubusercontent.com/lambdal/cifar10-fast/master/net.svg)

The default ImageFolder is not used here because here each fish category folder again has two types of images.

If directory is this way we use default Image Folder:
<pre>
Fishes<br />
  <t> |_Black Sea Sprat <br />
              |_img1<br />
              |_img2<br />
              |_img3<br />
   |_Gilt Head Bream
              |_img1
              |_img2
              |_img3`
</pre>
But in this case we have directory like this
<pre>
Fishes
   |_Black Sea Sprat 
              |_Black Sea Sprat 
                      |_img1
                      |_img2
                      |_img3
              |_Black Sea Sprat_GT
                     |_img1
                     |_img2
                     |_img3
              
   |_Gilt Head Bream
              |_Gilt Head Bream
                     |_img1
                     |_img2
                     |_img3
              |_Gilt Head Bream_GT
                     |_img1
                     |_img2
                     |_img3
</pre>   
So we explore on how to write CustomImageFolder
