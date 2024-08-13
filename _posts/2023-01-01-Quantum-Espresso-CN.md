---
layout: post
title: Quantum Espresso使用筆記
subtitle: 一個有關Quantum Espresso的簡易使用筆記，只涉及我自己感興趣的部分。你應該明白，這些內容僅供參考。
author: Shuci Lee
categories: QuantumEspresso
banner:
  image: https://bit.ly/3xTmdUP
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: QuantumEspresso Linux Vim MKL gcc gfortran openmpi wow
sidebar: []
---

Quantum ESPRESSO是一款開源免費的第一性原理程序，你可以在此[網站](https://www.quantum-espresso.org/)上註冊後下載code。

## 1. Rocky Linux 7.3 下安裝Quantum ESPRESSO 7.1

1. 安裝OpenMPI

   1.1 前往此[網站](https://www.open-mpi.org/)下載openmpi-5.0.2.tar.gz到本地文件夾，在該文件所在位置打開控制台。我的文件保存位置為:

   ```
   /home/apple/app
   ```

   你可以使用pwd命令查看當前文件所處位置，根據你的實際情況自行更改以下命令：

   ```
   pwd #查看文件所在位置
   tar -xzvf openmpi-5.0.2.tar.gz #解壓
   mkdir openmpi502 #創建一個名字為openmpi502的文件夾
   ls
   cd /home/apple/app/openmpi-5.0.2
   ./configure --prefix=/home/apple/app/openmpi502 #編譯到openmpi502
   make all install
   ```
   
   如果一切順利，鍵入以下命令：
   
   ```
   vi ~/.bashrc
   ```
   
   按下鍵盤上的Ins按鍵或者字母i，找到空白之處，鍵入以下內容：
   
   ```
   export PATH=$PATH:/home/apple/app/openmpi502/bin
   export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/apple/app/openmpi502/lib
   ```
   
   接著按下鍵盤上的Esc按鍵，輸入：
   
   ```
   :wq
   ```
   
   關閉當前控制台，重新打開，鍵入以下內容檢查OpenMPI是否可以正常調用：
   
   ```
   mpiexec -V
   ```
   
   如果出現版本號，那麼你就不需要再次開始一些無聊之事。
   
   

## section 2

test3

```cpp
#include <iostream>
using namespace std;

int main() {
  cout << "Hello World!";
  return 0;
}
// prints 'Hi, Tom' to STDOUT.
```
