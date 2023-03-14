安装过程：

安装JDK,NodeJS，AndroidStudio

## 02 flex

[使用 Flexbox 布局 · React Native 中文网](https://www.reactnative.cn/docs/flexbox)

![image-20221202185242037](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221202185242037.png)

![image-20221202185311845](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221202185311845.png)

## 03响应式布局

[使用 Flexbox 布局 · React Native 中文网](https://www.reactnative.cn/docs/next/dimensions)

使用这个dimensions.get()方法获取设备宽高，然后可以自己运算

```css
width:Dimensions.get('window').width/3
```



## 04核心组件

![image-20221202194448278](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221202194448278.png)

![image-20221202194536496](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221202194536496.png)

### 区分平台

这些直接看官网就行。

如何区分平台？[P14. 14.ActivityIndicator_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Pt4y1n7bD?p=14&spm_id_from=pageDriver&vd_source=570cea793fc3893804a63510f81f7ea7)11分

[Platform · React Native 中文网](https://www.reactnative.cn/docs/platform#os)

### View和SafeAreaView

![image-20221203151134071](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221203151134071.png)

### 动画

![image-20221203162951079](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221203162951079.png)

![image-20221203163039315](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221203163039315.png)

### 第三方组件

![image-20221203171850363](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221203171850363.png)

#### WebView

访问网址

[react-native-webview/react-native-webview: React Native Cross-Platform WebView (github.com)](https://github.com/react-native-webview/react-native-webview)

#### Picker

下拉列表

[react-native-picker/picker: Picker is a cross-platform UI component for selecting an item from a list of options. (github.com)](https://github.com/react-native-picker/picker)

#### Swiper

轮播图

[leecade/react-native-swiper: The best Swiper component for React Native. (github.com)](https://github.com/leecade/react-native-swiper)

#### AsyncStorage

异步存储

[react-native-async-storage/async-storage: An asynchronous, persistent, key-value storage system for React Native. (github.com)](https://github.com/react-native-async-storage/async-storage)

#### Geolocation

定位

[michalchudziak/react-native-geolocation: Geolocation APIs for React Native (github.com)](https://github.com/michalchudziak/react-native-geolocation)

#### Camera

照相机

[mrousavy/react-native-vision-camera: 📸 The Camera library that sees the vision. (github.com)](https://github.com/mrousavy/react-native-vision-camera)

[Getting Started | VisionCamera (mrousavy.com)](https://mrousavy.com/react-native-vision-camera/docs/guides/)

#### Image-Picker

调用摄像头，访问相册

[react-native-image-picker/react-native-image-picker: A React Native module that allows you to use native UI to select media from the device library or directly from the camera. (github.com)](https://github.com/react-native-image-picker/react-native-image-picker)

### 路由

