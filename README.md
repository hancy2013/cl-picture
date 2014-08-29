cl-picture
==================

通用图片管理系统


一、前置项目依赖

https://github.com/pumadong/cl-privilege

二、项目说明

图片管理，用于部署在一台单独的图片服务器，接收商品图片的上传，作为CDN服务器的源站，并提供简单的图片浏览、删除、上传功能。

图片管理主要是商品的图片管理，所以涉及的一些规则验证，基本是商品相关的。

图片名称规则：商品编号_01_图片类型.jpg，商品编号：8-10位数字，01：商品序号，代表第一个位置，图片类型：o、l、m、s、t、b，第一个位置的图片切一个c。

o(1000*1000)，original，原始图片

l(480*480)，large，大图

m(240*240)，middle，中图

s(160*160)，small，小图

t(60*60)，tiny，微小图

b(750*750)，baby，宝贝描述图

c(40*40)，color，颜色图，单品页展示用

三、Jquery插件

Jquery Ajax File Uploader	: http://www.phpletter.com/DOWNLOAD/

因为Ajax是不能跨域的，这个插件的作用是生成一个隐藏的Form来提交，并定义一个本域的jsp文件用于接收处理结果。

对于文件上传来说，应该实现选择多个目录，批量上传，这个是B/S结构的商品管理要考虑的技术问题。

四、其他


图片管理，可以有自动切图功能，直接输入包含尺寸的url，自动切出需要的尺寸。

图片越来越大，单台机器不能满足要求时，可以引入Gearman之类的分布式图片管理框架。