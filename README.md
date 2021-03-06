# 微信小程序开发笔记

### ColorUI 框架的使用

1. 下载源码解压，将 `demo `文件夹中的 `colorui` 文件夹复制到小程序根目录

2. 在小程序 `app.css` 文件中添加以下代码

   ```css
   @import "colorui/main.wxss";
   @import "colorui/icon.wxss";
   @import "colorui/animation.wxss"
   ```

3. 使用微信开发者工具打开 `demo` 文件夹

4. 找到自己想用的组件或者基础元素，通过左下方的页面路径找到对应代码，复制到自己的项目中即可

   ![image-20210808222406785](F:/goodgoodstudy/Notes/README.assets/image-20210808222406785.png)

### 页面开发小技巧总结

#### 尺寸

官方上规定屏幕宽度为20rem，规定屏幕宽为750rpx

也可用比例调整尺寸，`1vh`相当于百分之一屏幕高度，`1vw`相当于百分之一屏幕宽度

#### 背景图片

![image-20210808225548651](F:/goodgoodstudy/Notes/README.assets/image-20210808225548651.png)

类似这种设计，可以不需要什么麻烦的绘图，直接把内部扣掉做成文本的背景图

#### scroll-view

为避免`scroll-view`带动整个页面滚动，样式中固定高度即可



### 小程序页面跳转携带参数

```js
var that = this;

wx.redirectTo({
      url: "../activityLimit/activityLimit?activityId=" + that.data.activityId,
});
```



### 跳转至新页面之后 onLoad 函数不执行

1. 在页面跳转函数中添加函数执行成功的回调函数

```js
var that = this;

wx.navigateTo({
  url: "../activityLimit/activityLimit?activityId=" + that.data.activityId,
  success: function (e) {
    var page = getCurrentPages().pop();
    if (page == undefined || page == null) return;
    page.onLoad();
  },
});
```

2. 将 onLoad 函数中的语句写入 onShow 函数

 ```js
  onShow: function () {
    // 获取当前小程序的页面栈
    let pages = getCurrentPages();
    // 数组中索引最大的页面--当前页面
    let currentPage = pages[pages.length - 1];
    // 打印出当前页面中的 options
    this.setData({
      activityId: currentPage.options.activityId,
    });
  }
 ```

   







































