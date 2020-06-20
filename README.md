<h1 align="center">Beyond The FRONTIER</h1>

<p align="center">
    <a href="https://www.tensorflow.org/">
        <img src="https://img.shields.io/badge/Tensorflow-1.13-green" alt="Vue2.0">
    </a>
    <a href="https://github.com/CuiJiali-CV/">
        <img src="https://img.shields.io/badge/Author-JialiCui-blueviolet" alt="Author">
    </a>
    <a href="https://github.com/CuiJiali-CV/">
        <img src="https://img.shields.io/badge/Email-cuijiali961224@gmail.com-blueviolet" alt="Author">
    </a>
    <a href="https://www.stevens.edu/">
        <img src="https://img.shields.io/badge/College-SIT-green" alt="Vue2.0">
    </a>
</p>

### Overviews of history and details in graph deep learning

<br /><br />

#### 非欧空间下的卷积操作

* ##### 基本卷积（欧式空间）	

  * 卷积形状不可变 固定
  * ![Image text](https://github.com/CuiJiali-CV/Graph-Learning-Note/raw/master/img/basic_conv.png)

* #####  活性卷积（CVPR 2017):

  * ![Image text](https://github.com/CuiJiali-CV/Graph-Learning-Note/raw/master/img/activate_conv.png)

  * 双线性插值：离散坐标下，通过插值的方法计算得到连续位置的像素值

  * 学习的参数
    $$
    \Delta\alpha_k,\Delta\beta_k
    $$

  *  缺点：可变卷积核的形状固定，对于不同数据集无法适应

* ##### 可变形卷积（ICCV 2017)

  * ![Image text](https://github.com/CuiJiali-CV/Graph-Learning-Note/raw/master/img/change_conv.png)

  * 卷积核位置参数化， 双线性插值连续化，传统BP算法训练.

  * 箭头表示格子的偏移量，而偏移量由数据训练得来的。结构是end2end的，所以可以使用BP训练。

  * <img src="https://latex.codecogs.com/gif.latex?y(p_0)=\sum_{p_n\in&space;R}w(p_n)\cdot&space;x(p_0&plus;p_n)" title="y(p_0)=\sum_{p_n\in R}w(p_n)\cdot x(p_0+p_n)" />

  * <img src="https://latex.codecogs.com/gif.latex?R={(-1,-1),(-1,0),...,(0,1),(1,1)}" title="R={(-1,-1),(-1,0),...,(0,1),(1,1)}" />

  * <img src="https://latex.codecogs.com/gif.latex?y(p_0)=\sum_{p_n\in&space;R}w(p_n)\cdot&space;x(p_0&plus;p_n&plus;\Delta&space;p_n)" title="y(p_0)=\sum_{p_n\in R}w(p_n)\cdot x(p_0+p_n+\Delta p_n)" />

  * <img src="https://latex.codecogs.com/gif.latex?x(p)=\sum_{q}G(q,p)\cdot&space;x(q)" title="x(p)=\sum_{q}G(q,p)\cdot x(q)" />



    

  * (1)(2)讲述的是在规则的R空间下（3x3), 非连续pn

  * (3)(4) 现在加入了 delta pn，使其连续化，并且通过G(q,p)不断学习 delta pn

  * ![Image text](https://github.com/CuiJiali-CV/Graph-Learning-Note/raw/master/img/change_conv2.png)

  * 每个位置对应一个偏移量，偏移通过额外的卷积学习。

  

<br /><br />

## Solutions

#### As a video are about the objects (content) performing actions(motion), the latent space of images should be further decomposed into two subspaces, where the deviation of a point in the first subspace(content) leads content changes in a video clip and the deviation in the second subspace(motion) results in temporal motions.

- In this way, the video of an action with different execution speeds will only result in difference in the motion space.
- Also, decomposing motion and content allows to control the changing of the video. Consider **changing the content representation while fixing the motion space**, we could have the video of different objects performing the same motion pattern. **By changing the motion space while fixing the content representation**, we could have the video of the same objects performing different motion pattern.



## Process

- ##### Overall

  - it generates a video clip by sequentially generating video frames. At each time step, an image generative network maps a random vector to an image. The random vector consists of two parts where the first is sampled from a content subspace and the second is sampled from a motion subspace. 
  - Since content in a short video clip usually remains the same, it models the content space using a Gaussian distribution and use the same realization to generate each frame in a video clip. On the other hand, sampling from the motion space is achieved through a recurrent neural network where the network parameters are learned during training.

  












## Author

```javascript
var iD = {
  name  : "Jiali Cui",
  
  bachelor: "Harbin Institue of Technology",
  master : "Stevens Institute of Technology",
  
  Interested: "CV, ML"
}
```
