# Deep-Reinforcement-Learning-Snake-AI

## 环境依赖

* Python 3.6.2
* TensorFlow 1.3.0
* Pygame
* OpenCV

## 如何运行

* `python play.py` 进行游戏
* `python train.py` 训练模型

## Deep Q network 算法

```
Initialize replay memory D to size N
Initialize action-value function Q with random weights
for episode = 1, M do
    Initialize state s_1
    for t = 1, T do
        With probability ϵ select random action a_t
        otherwise select a_t=max_a  Q(s_t,a; θ_i)
        Execute action a_t in emulator and observe r_t and s_(t+1)
        Store transition (s_t,a_t,r_t,s_(t+1)) in D
        Sample a minibatch of transitions (s_j,a_j,r_j,s_(j+1)) from D
        Set y_j:=
            r_j for terminal s_(j+1)
            r_j+γ*max_(a^' )  Q(s_(j+1),a'; θ_i) for non-terminal s_(j+1)
        Perform a gradient step on (y_j-Q(s_j,a_j; θ_i))^2 with respect to θ
    end for
end for
```

## CNN 结构

![](https://ws2.sinaimg.cn/large/006tNc79ly1fnb6yvfce4j30o707s402.jpg)

## 效果展示


* Frames 0 (0h)

![](https://ws4.sinaimg.cn/large/006tNc79ly1fn9ayrzu63g30d50agtj3.gif) 

* Frames 1500000 (+8h)

![](https://ws3.sinaimg.cn/large/006tNc79ly1fn9b5r6y65g30d50agn9b.gif)

* Frames 3000000 (+20h)

![](https://ws1.sinaimg.cn/large/006tNc79ly1fn9bho09vug30d50agwy0.gif)

* Frames 11000000 (+56h)

![](https://ws2.sinaimg.cn/large/006tNc79ly1fnbgv5dkysg30d50ag4n2.gif)

## 参考资料
* [Guest Post (Part I): Demystifying Deep Reinforcement Learning](https://ai.intel.com/demystifying-deep-reinforcement-learning/)
* [Guest Post (Part II): Deep Reinforcement Learning with Neon](https://ai.intel.com/deep-reinforcement-learning-with-neon/)
* [Using Deep Q-Network to Learn How To Play Flappy Bird](https://github.com/yenchenlin/DeepLearningFlappyBird)
* [Source Code to Wormy](https://inventwithpython.com/pygame/chapter6.html)

