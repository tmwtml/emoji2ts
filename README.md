## Emoji Selector

Midterm project for Time series mining class, Computer Engineering, Chulalongkorn University


### Team member
- Thanyaporn Phinthuphan 	5830242621
- Nitipat Jaidee			5831032321

### Overview
In our project, we tried to convert emoji images into time series data. This will help when you want to convert your own emoji hand-drawing into real emoji images. We selected 15 emoji images that cover all popular emotion as shown in the path emoji/original folder. 

### Algorithm
We divided the algorithm into 3 parts; preprocessing, conversion, matching.

#### Part 1: Preprocessing
In this part, we tried to convert original emoji images (Fig.1) into black and white images using python3. We change the yellow face into white color and other colors into black color. After that, we resize the images into 512 x 512 pixel.

#### Part 2: Conversion
We tried to convert black and white emoji images into time series data by measure distance between the edge of the image and the first black pixel of the row or column. We measure this around the edge of the image then join them by left, bottom, right, top edge into a time series data with a length of 2048.

#### Part 3: Matching
We calculated 15 time series data from all emoji images and collected them in a cache. When we got some input as emoji hand-drawing images. We tried to convert them into time series data by the algorithm in part 2. After that, we convert them into real emoji images by calculated DTW distances between time series data of the test image and 15 templates and selected the emoji image of the template that got the minimum distance. We used ‘dtaidistance’ python library to calculate DTW distance. The result will be shown with a hand-drawing image, matched emoji image and time series data of both images (hand-drawing as blue, matched emoji as orange).

The implementation of all part with python3 can be reached in the file emoji2ts.ipynb and all images for testing are in emoji folder.

### Usage
We can use this concept to implement a ‘Emoji Selector’ that can select emoji from hand-drawing emoji. Users can draw their own emoji and ‘Emoji Selector’ will select the most similar real emoji images and show it to users like this.

### Result
We tested our ‘Emoji Selector’ with 45 emoji hand drawing images (3 images per 1 emotion). Some of the tested images are shown in Figure 5. We found that have only 7 false matching result or we can say that our program has 84.44% of accuracy.

### Reference
- Emoji images: https://www.flaticon.com/packs/emoticons-4
- dtaidistance library: https://github.com/wannesm/dtaidistance
