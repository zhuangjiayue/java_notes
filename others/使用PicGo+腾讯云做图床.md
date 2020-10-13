# 1 概述

## 1.1 什么是图床

使用markdown记笔记写博客或者上传github时，图片的管理是个麻烦的问题。因此，图床是一个进行图片管理的工具。图床的定义如下：“就是专门用来存放图片，同时允许你把图片对外连接的网上空间，不少图床都是免费的。”市面上的图床有腾讯云对象存储，阿里云对象存储，七牛云和又拍云等对象存储产品，有些人也用github和gitee作为存储。

## 1.2 本文图床方案

基于需求和成本的考虑，我使用腾讯云+PicGo这个组合进行图床管理。其中：

- 腾讯云是一款比较便宜的对象存储产品，对于个人而言不贵，而且还送了我半年的试用期；
- PicGo是方便图片上传和将存储后的图片转化为markdown链接的软件，有了它图片上传变得非常简单。

# 2 腾讯云

首先登陆打开腾讯云，同时登陆，左上角选择产品，然后选择对象存储

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012232631184.png)

进入该页面，直接选择立即使用

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012232733596.png)


如果腾讯云账号未实名认证，则需要进行实名认证

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012232922805.png)


认证完毕，选择同意条款开通服务

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012233410883.png)


选择创建存储桶

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012233557443.png)


凭个人的需求和要求填写相关资料，点击确定

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012233649340.png)


到此，一个存储桶就生成了。存储桶我的个人理解类似于图片文件夹，如果需要多个存储桶则可以点击创建存储桶继续创建。

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012233804246.png)




点击存储桶，进入存储桶

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012233943652.png)


点击上传文件

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012234003007.png)

选择文件，然后选择上传，图片就成功上传到腾讯云了。

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012234149254.png)


点击详情，然后获取下方的对象地址，就可以在markdown中使用图片了

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012234222177.png)


# 3 PicGo

如果每次上传图片都要打开腾讯云进行上传，然后点击详情获取照片地址，那步骤一定很麻烦。腾讯云对象存储有提供软件进行管理，但我使用的是一款更方便的开源软件PicGo。PicGo的介绍和下载地址请参考项目地址：https://github.com/Molunerfinn/PicGo 

我在下的版本是2.2.2，下载完常规安装即可。安装完打开软件界面如下：（没显示界面的查看下右下角缩略图）

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012234717202.png)


依次点击图床设置，腾讯云cos

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012234913044.png)


这里需要填写六个选项。首先关于SecretId和key的方式获取如下。回到腾讯云，右上角账号下的访问管理，

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012235304343.png)


然后点击访问密钥，API密钥管理

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012235526174.png)


继续使用，然后新建密钥

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012235612727.png)


腾讯云后台会自动创建生成SecretId和key，将两者填入PicGo页面即可

然后是APPID，存储空间名和存储区域。回到腾讯云的存储对象，点击存储桶列表。以下图为例，三者分别为：test，1303904915和nj。特别注意的是，存储区域需要填入地区名的两个首写字母。

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012235827784.png)


最后一个是设定自定义域名，可以从任意一张图片，查看其对象地址，然后复制https://**.com填入即可。

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201012234222177.png)


全部填写完毕后，点击设为默认图床和确定即可。到这里就设置完毕了。

接着点击右上角，PicGo会变成一个小圆球，如下

![](https://jiayue-1258324758.cos.ap-nanjing.myqcloud.com/image-20201013000112004.png)


可以将图片拖到小球内，如果上传成功会有上传成功的提示信息，接着PicGo会自动生成markdown地址到粘贴版，直接粘贴即可。

# 附注

如有错误，请多指正。如有帮助，请点个赞。