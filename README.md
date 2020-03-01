# script_arknight
<p align="left">
	<img src="https://github.com/vertuer/script_arknight/blob/master/processed/f9c6cbdc6b.jpg" width="250" height="250">
</p>

## 1.简介
  [EXE文件网盘链接3-1](https://pan.baidu.com/s/1Ko6P6jvU7c2LEFEa2zg9Pw)  
  提取码：p2to   
  自己写的针对windows模拟器（支持夜神模拟器及mumu（需管理员模式打开））的游戏脚本，现在能自动接取并完成悬赏及一些蛋疼操作，使用请注册github打个star，可以使用源码二次开发，源码使用请fork，欢迎留言交流。  
  提示：不推荐星河区使用！
  有疑问及建议可以加QQ2434995342,有空回答相关疑问

明日方舟调用库：  
PIL，pywin32-223，opencv-3.4.3  



## 2.基本原理说明：
  利用抓取windows窗口图像，并对图像进行基本识别操作后对模拟器窗口发送虚拟操作指令，由于是在模拟器之外的，因此原理上不会有风险。
缺点是模拟器无法最小化，因windows程序最小化停止重绘窗口，无法抓取到窗体图像。推荐spy++这个工具，可以获取模拟器的句柄和窗体信息，[spy++下载地址](http://pan.baidu.com/s/1skMJUkH)
  ocr识别思路：阈值分析，连通域分割，hog特征处理，svm分类。

## 3.脚本功能（针对2020-3-1版本）
  1. 自动接取悬赏，可以指定悬赏类型及悬赏箱子个数    
  2. 自动完成悬赏，自动组队并完成悬赏，关卡结束自动召回队友，战斗中自动释放绝学，遇到特殊情况（如队友掉线等）自动退队重组
  3. 自动绝学挂机
  4. 自动抢摆摊
  5. 自动抢集市
  6. 自动抢红包
  7. 自动采集（暂定，点了也没用，我还没写）
  8. 脚本开始位置有要求，详情见下  
  9. 分辨率并不能自适应，一梦江湖图标一堆半透明加文字的，目前只测试了1340x779的分辨率，即桌面分辨率为1080p下打开的默认分辨率 
  10. 暂时只支持PC客户端
## 4.挂机界面使用说明  
  简易界面如下  
<p align="left">
	<img src="https://github.com/vertuer/ymjh/blob/master/123.png" width="200" height="300">
</p>

  1. 仅接悬赏：请在悬赏界面使用，开始后可以点击右侧“停止”按钮中断。该功能为接三个悬赏，悬赏盒子数量和类型自行设定。  
  2. 自动悬赏：请在主界面使用，使用前自己创建好队伍（对人数没有要求，之后会组），队伍目标选择江湖纪事中的任意一个（如咸鱼港新秀等），之后点击开始
  3. 抢红包：请打开聊天界面，保证左侧第三频道为世界，并且注意保证信息滚动。除了绝学挂机应该不能与其它功能共同使用  
  4. 绝学挂机：请切到端游模式（手游模式非战斗状态脚本无法使用），然后1-8对应8个技能，根据自身职业选择放对应技能（防止挂机过久位移到河里），初始设定是沧海职业的（我玩的沧海），绝学挂机推荐和抢红包一起使用  
  5. 抢集市：在集市界面的“购买”子菜单下使用，根据情况选择刷新速度  
  6. 抢摆摊：进入摆摊gui，应该比较明了，是否多个购买功能是一次性买9个，不勾选速度会快一点点  
  7. 因为主要是自己使用，有使用问题请加企鹅      
  8. 开启脚本时要用管理员模式，分辨率一定要喂1340x779，微小偏差没有问题。
  
## 5.摆摊界面使用说明  
  简易界面如下
<p align="left">
	<img src="https://github.com/vertuer/ymjh/blob/master/456.png" width="200" height="300">
</p>

## 注意事项  
  1. 程序通过截取的图像判断关卡位置及当前进入的关卡是否正确，整体逻辑判断大致为 总章节（主线、芯片、物资、活动）-> 子章节（第一章、龙门币等）->具体关卡信息（1-7等）->判断是否为脚本正在处理的关卡  
  2. 因此若要添加关卡图库，则需要两张图，第一张是能够让脚本找到这个关卡的位置，第二则是点击关卡后能够判断进入正确的相关信息，如关卡的中文名称  
## 简易流程  
  1. 通过“打开文件”或者是“模拟器图像载入”加载图像  
  2. 在左侧图像中按住鼠标左键选取截图区域  
  3. 点击右侧“开始图像匹配”，若只有选择关卡区域，则表示截取的图像可以使用  
  4. 左键选中想要添加的图库的上一级目录，右键“添加”  
  5. 输入关卡或章节名称，确定  
  6. 若需要添加关卡则还要添加上述注意事项2介绍的关卡确认图库，添加完后程序自动保存关卡信息  

## 6.后续增加功能：
  1. 脚本自动更新
  2. 用户可以通过添加图库自行添加想刷的关卡，类似于按键精灵（ok）  
  3. 自己编写特征匹配函数dll  
  4. 优化代码结构  
  5. 咕咕咕  

  
## 7.更新内容
### （2020-3-1）
  

