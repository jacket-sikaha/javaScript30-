## 02 - 时钟clock

### 介绍

#### 		打开网页就会读取并显示电脑当前时间。

### 设计思路

1.  处理三只指针的样式以便区分：如scale(0.9,0.9)    对应高，宽

2. 处理三只指针位置，使其在钟盘中间：

   ```css
    /*修改模型偏移位置重心 第一个参数默认左右，第二个默认上下*/
    transform-origin: 100%;
    /*模型偏转角度*/
    transform:rotate(90deg);
   ```

3. 获取实时时间new Date() ------ [Date对象操作](https://www.w3school.com.cn/jsref/jsref_obj_date.asp)

4. 将获得的时，分，秒   几个变量分别进行处理，与钟盘三种指针的角度变化相对应，以便指针偏转弧度随时间的更新变化

5. setInterval不断调用以此更新数据，呈现时间流动效果

### 注意问题

1. 如59s -> 0 s  这是获取时间的变化，因此需要考虑圈数问题，不然会出现动画错乱问题（354 -> 0 的大幅移动），应该是 354 -> 360

