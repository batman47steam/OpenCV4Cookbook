#### Chapter 9

##### std::nth_element

http://m.biancheng.net/view/7476.html

https://en.cppreference.com/w/cpp/algorithm/nth_element

> 当采用默认的升序排序规则`std::less<T>`时，该函数可以从某个序列中找到第n小的元素K，并将K移动到序列中第n的位置处，不仅如此，整个序列经过`nth_element()`函数处理后，所有位于K之前的元素都比K小，所有位于K之后的元素都比K大

##### cv::DMatch

用于保存匹配成果的结果

**queryIdx: ** 查询点的索引（当前要寻找匹配结果的点在它所在图片上的索引）

**trainIdx: ** 被查询到的点的索引 （存储库中的点在存储库上的索引）

**distance: ** 两个描述子之间的距离

