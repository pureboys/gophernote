---
title: "Mac下配置多版本java"
summary: "Mac下配置多版本java"
date: 2023-06-12
categories: 
  - "program"
tags: 
  - "java"
  - "mac"
---

### 安装好不同版本的jdk

```shell

brew install openjdk@17
sudo ln -sfn /opt/homebrew/Cellar/openjdk@17/17.0.7/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk

brew install openjdk@11
sudo ln -sfn /opt/homebrew/Cellar/openjdk@11/11.0.19/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
```

### 配置.zshrc

```shell

javahome() {
  unset JAVA_HOME 
  export JAVA_HOME=$(/usr/libexec/java_home -v "$1");
  java -version
}
alias j11='javahome 11'
alias j17='javahome 17'

```

### 在终端使用配置
```shell
# 使用java 11版本
j11
# 使用java 17版本
j17
```