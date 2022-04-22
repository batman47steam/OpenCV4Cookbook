## Opencv4

从opencv3->opencv4发生改变的一些东西

https://github.com/laganiere/OpenCV3Cookbook

### 2022-4-20

#### Chapter 9

opencv3 -> opencv4

`cv::xfeatures2d::SIFT` -> `cv::SIFT`

`cv_TM_SQDIFF` -> `cv::TM_SQDIFF`

`cv_LOAD_IMAGE_GRAYSCALE` -> `cv::IMREAD_GRAYSCALE`

### 2022-4-22

#### Chapter 10

In `cv::drawMatches` change `2` to `cv::DrawMatchesFlags::NOT_DRAW_SINGLE_POINTS`

> 这个按道理是完全等价的，不过在vs上会报错

add `cv::` namespace for `Stitcher`

