---
layout: post
title: "Xcode 8安装CocoaPod以及遇到的小问题"
date: 2017-3-18
tags: 工具   
---

由于新换了电脑，不得不重新安装一下CocoaPods，仅以此文分享一下安装过程以及遇到的问题。

## 一 选择镜像

我之前选择了ruby镜像，但是通过命令行安装的时候报错Error:路径下错误，然后我找到了路径删除了.rvm下的所有文件。决定重新安装。这次选择taobao镜像。

移除默认的ruby源：

$ gem sources --removehttps://rubygems.org/
选择taobao镜像:

$ gem sources -ahttps://ruby.taobao.org/

### 二 查看是否安装成功

查看是否安装成功:

$ gem sources -l
当出现以下信息时证明安装成功了哈

*** CURRENT SOURCES ***

https://gems.ruby-china.org

https://ruby.taobao.org/
mac 10.11之上的系统使用如下命令，(我的是10.12)安装CocoaPods:
$ sudo gem install -n /usr/local/bin cocoapods
注意:我在此处检查的时候安装的时候遇到了一个问题，内容如下

ERROR:While executing gem ... (Gem::RemoteFetcher::FetchError)

bad response Forbidden 403 (https://gems-ruby-china.b0.upaiyun.com/quick/Marshal.4.8/cocoapods-core-1.2.0.gemspec.rz)
无效的操作，推测应该gem版本有问题，可以用一下命令查一下ruby和gem的版本号：

$ gem -v
$ ruby - v
查看之后重新更新一下gem

$ sudo gem update --system
然后会显示Latest version currently installed. Aborting.这就是最新的gem已经更新了，你可以使用了。

### 三 安装成功

再重新安装CocoaPods

$ sudo gem install -n /usr/local/bin cocoapods 
设置pods

$ pod setup
显示Setup completed就表示完成了。








