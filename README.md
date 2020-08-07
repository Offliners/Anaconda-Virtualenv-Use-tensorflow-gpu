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

#### 4. 進入虛擬環境
建立完成後，輸入`activate test_env`進入虛擬環境

![image7](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image7.PNG)

當前方出現自己的環境名稱表示進入成功

![image8](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image8.PNG)

#### 5. 安裝tensorflow-gpu
輸入`pip install tensorflow-gpu==1.13.1`，安裝版本為1.13.1的tensorflow-gpu

![image9](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image9.PNG)

#### 6. 安裝 CUDA 10.0
進入此網站 : https://developer.nvidia.com/cuda-toolkit-archive

![image10](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image10.PNG)

尋找`CUDA 10.0`並安裝

![image11](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image11.PNG)

一直按`下一步`就安裝完成

![image12](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image12.PNG)

確認是否有加入環境變數，在Window搜尋`環境變數`

![image13](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image13.PNG)

CUDA安裝軟體基本上會自動填入路徑

![image14](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image14.PNG)

#### 安裝cuDNN 7.6.5
進入此網站 : https://developer.nvidia.com/rdp/cudnn-archive

找到cuDNN 7.6.5 for CUDA 10.0

![image15](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image15.PNG)

安裝`Window 10`版的

![image16](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image16.PNG)

下載完檔案後解壓縮會出現3的資料夾與1個文字檔

![image17](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image17.PNG)

將整個複製到`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0`中

![image18](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image18.PNG)

再進入環境變數看系統變數中的Path中，雙擊兩下可看到系統路徑

![image19](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image19.PNG)

是否有剛剛複製cuDNN的`bin`與`libnvvp`路徑，基本上系統會自動添加，若沒有需要手動加入

![image20](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image20.PNG)

#### 確認是否安裝成功
回到`Anaconda Prompt`，進入已創建的虛擬環境，輸入`nvcc -V`

若有跑出此畫面表示`CUDA 10.0`安裝成功

![image21](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image21.PNG)

接著輸入`python`

![image22](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image22.PNG)

輸入以下指令
```python
from tensorflow.python.client import device_lib
print(device_lib.list_local_devices())
```
[code](test.py)

![image23](https://github.com/Offliners/Anaconda-Virtualenv-Use-tensorflow-gpu/blob/master/image/image23.PNG)

若有讀取到NVIDIA顯卡表示`tensorflow-gpu`安裝成功，在此虛擬環境中的tensorflow都會使用GPU來計算
