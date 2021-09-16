## 附录F.1 transcode

>  转码标志，不携带此字段或传**0**表示不转码，传**1**或**2**表示转码。

| 类型    | 类型说明 |
|---------|----------|
| 0      | 不转码   |
| 1      | 组件转码  |
| 2      | 设备转码，仅支持分辨率、比特率、帧率转码参数进行转码 |

**举例**：
transcode=1&resolution=D1&bitrate=512&framerate=15&videotype=h264&systemformat=rtp&audiotype=G711U&samples=8000&audiobitrate=64000&bitspersample=16

特殊说明：可以只填写部分参数，表示只有这些参数需要转码。


### 附录F.1.1 resolution：分辨率

>  取值范围：

>  组件转码：QCIF（176*144），QVAG（320*240），CIF（352*288），2CIF（704*288），D1（720*576），720P（1280*720），1080P（1920*1080）；

>  设备转码：QCIF（176*144）、NCIF(320*240)、CIF(352*288)、VGA（640*480）、HCIF（704*288）、FCIF（704*576）、D1(960*576)、720P（1280*720）、920P（1280*960）、1080P（1920*1080）、AUTO

**举例**：
transcode=2&resolution=CIF


### 附录F.1.2 bitrate：比特率

>  取值范围：

>  组件转码：最小值是128Kbps，最大值是8192Kbps

>  设备转码：最小值是128Kbps，最大值是16384Kbps

**举例**：
transcode=2&framerate=15


### 附录F.1.3 framerate：帧率

>  取值范围：

>  组件转码：1-25

>  设备转码：1-30、1/2、1/4、1/8、1/16


**举例**：
transcode=2&bitrate=512


### 附录F.1.4 videotype：视频编码类型

>  取值范围：h264

**举例**：
transcode=1&videotype=h264


### 附录F.1.5 systemformat：视频封装格式

>  取值范围：rtp、ps

**举例**：
transcode=1&systemformat=rtp


### 附录F.1.6 audiotype：音频编码

>  取值范围：G711U、G711A、G722、AAC

#### G711U/G711A

| 采样率/比特率           | 样位率 |
| ----------------------- | ------ |
| 采样率8000，比特率64000 | 16     |

#### G722

| 采样率/比特率            | 样位率 |
| ------------------------ | ------ |
| 采样率16000，比特率16000 | 16     |

#### AAC

| 采样率/比特率                                                | 样位率 |
| ------------------------------------------------------------ | ------ |
| 采样率8000，比特率16000、32000                               | 16     |
| 采样率16000，比特率16000、32000、64000                       | 16     |
| 采样率32000、44100、48000，比特率16000、32000、64000、128000 | 16     |


**举例**：
transcode=1&audiotype=G711U


### 附录F.1.7 samples：采样率

>  单位：赫兹（Hz）

**举例**：
transcode=1&samples=8000


### 附录F.1.8 audiobitrate：音频比特率

>  单位：bps

**举例**：
transcode=1&audiobitrate=64000


### 附录F.1.9 bitspersample：样位率

**举例**：
transcode=1&bitspersample=16


### 附录F.1.10 intervalType 包间隔类型字段，用于推流时告知媒体服务数据包的间隔类型

>  取值范围：gbTcp

**举例**：
transcode=1&intervalType=gbTcp

说明：在国标解码器TCP推流时，需要在URL中增加streamform=gb28181&intervalType=gbTcp两个字段，用于告知媒体服务此时需要出国标流，并且以国标TCP定义的包间隔类型发送。


### 附录F.1.11 snapshot：是否是缩略图

>  取值范围：0表示不是缩略图，1表示是缩略图

**举例**：
transcode=1&snapshot=1

### 附录F.1.12 secondskip：时间间隔（按时间段，时间间隔获取图片时使用）

>  取值范围：1-86400，单位：秒

**举例**：
transcode=1&secondskip=10

secondskip设置为10，时间段是1点到2点，相当于在1点到2点的录像中，每10秒抓取一张缩略图



</br></br></br></br></br>