# Anaconda Virtualenv Use tensorflow-gpu
## 測試環境
作業系統 : `Window 10 64bit`
   
顯卡 : `NVIDIA Geforce GTX 1050`
## 事前準備
#### 1. 確認電腦是否有NVIDIA顯卡

可以從裝置管理員中顯示卡看電腦是否有NVIDIA顯卡

![image1](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image1.PNG)

#### 2. 查詢此顯卡的計算能力
可從此網址查詢到 : https://developer.nvidia.com/cuda-gpus

建議顯卡計算能力(Compute Capability) 大於3.5以上，使用tensorflow-gpu才會有明顯的成效

![image2](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image2.PNG)
## 安裝步驟
#### 1. 安裝Anaconda
到Anaconda官方網站下載 : https://www.anaconda.com/products/individual

安裝一直`next`過去就好

![image3](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image3.PNG)

#### 2. 打開Anaconda Prompt

![image4](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image4.PNG)

#### 3. 建立虛擬環境
在命令列輸入`conda create -n test_env pip python=3.6`，test_env是環境名稱，可以自己取，然後Python的版本是3.6

![image5](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image5.PNG)

這裡輸入`y`

![image6](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image6.PNG)
