## IOS端测试

参考书籍：腾讯IOS测试实战

## 一、IOS的基础知识

### IOS的特殊性
#### 1.证书

#### 2.越狱
#### 3.灰度
#### 4.AppStore审核

## 二、IOS的自动化测试工具
IOS的测试工具较少，但是可以对其进行框架的二次开发即可实现。
- UITest
- Appium

## 三、IOS兼容性测试
### 1.系统兼容
#### 1.1 新增功能
#### 1.2 接口差异
### 2.机型兼容
#### 2.1 新增功能
#### 2.2 屏幕变化
#### 2.3 处理器差异
注意模拟器并不运行ARM代码，软件会被编译成x86可以运行的指令，因此适配不能在模拟器上进行验证。

## 四、IOS性能测试

性能测试的介入阶段

![](https://github.com/SolerHo/Software-Testing/blob/master/IOS%E7%AB%AF%E6%B5%8B%E8%AF%95/Images/%E6%80%A7%E8%83%BD%E6%B5%8B%E8%AF%95%E7%9A%84%E4%BB%8B%E5%85%A5%E9%98%B6%E6%AE%B5.png)

性能测试主要包括三个方向：

### 1.响应的及时性
指软件对用户操作指令做出响应的速度。

对于浏览器而言，可以把用户感受到的响应时间划分为

- **“呈现时间”** :指客户端在接收到网站数据时呈现页面所需的时间
- **“系统响应时间”**:指客户端接收到用户请求到客户端接收到服务器发来的数据所需的时间。又细分为：
	- 客户端收到请求到服务器收到客户端请求
	- 服务器处理时间、
	- 服务器向客户端回传数据的时间。

#### 响应速度的测试方法
#### 什么是响应速度？

完成某一项操作到预期结果显示完成所需要的时间，这段时间越短越好。

常见的响应速度测试方法：
- 掐表计时法
- 日志计时法
关键节点通过接口打印出有用的日志，然后人工或用脚本分析这些日志即可。
- 录像分帧计时法
测试过程中频率范围一般设置为`20～50帧`，这样测试结果就会有`40～100 ms`的误差范围，视具体情况而定。

### 2.运行的稳定性
指软件功能的稳定运行以及软件整体的稳定。

#### 稳定性测试的思路

- 一种是获取当前页面的所有控件，随机对某一个控件进行某一项操作
- 另一种是随机抓取某一个像素点，并在屏幕上点击该点。

### 3.资源的占用率。

每款软件都必须面对的一个问题。安装时占了多少硬盘空间、使用时占了多少内存等都是需要考虑的。

移动端中的要测试的三个维度：
- 电量测试
	- 电量测试通常的做法：
		- 1.关闭所有其他后台程序，只留一个被测试程序。
		- 2.关闭系统的所有不必要功能，如蓝牙、定位、热点、声音等。
		- 3.保持亮度一致。
		- 4.保证每次测试电量一样，最好的办法是把电量充满。
		- 5.以固定的操作执行被测试程序一段时间，最好在2小时以上。常用录制回放的方式来保证每次操作的一致性。
		- 6.测试完成后记录当前剩余电量。
- 流量测试
	- 流量测试的方法
		- 系统流量统计方法
		- 数据包分析法
- 内存测试

## 六、性能测试常见的测试框架
![](https://github.com/SolerHo/Software-Testing/blob/master/IOS%E7%AB%AF%E6%B5%8B%E8%AF%95/Images/%E5%B8%B8%E8%A7%81%E7%9A%84%E6%B5%8B%E8%AF%95%E6%A1%86%E6%9E%B6.png)

UITest是单元测试和UI自动化测试的利器。

## 七、IOS自动化测试

### 1.自动化测试适用的场景
#### 1.1 模块比较稳定的回归测试
该场景又分为：功能`基本稳定的UI自动化测试`和`接口基本不变的接口测试`。
#### 1.2 极限操作的测试
适用于一些手工测试覆盖不到的情况。

#### 1.3 长时间监控类测试
最常见的监控，包括协议、功能的监控。
#### 1.4 性能测试

### 2.自动化测试的框架

#### 2.1 接口自动化测试
不涉及UI界面，以`逻辑模块接口`为主要的测试

#### 2.2 UI自动化测试
直接在`应用层`上操作App，`模拟用户操作行为`的测试。

接口测试的范围包括：`协议测试、前后端协议的MOCK操作、接口选取、工具选取或者自己开发`。

在IOS端推荐的接口测试工具：
- XCTest
- Postman
