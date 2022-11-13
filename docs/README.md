# AWS Live Streaming
## 未必正確，brainstorm下
*基本考量係*：
- Streaming 或者 ODV
- 輸入方式
    - *Stream* - OBS, Youtube...
    - *ODV* - S3 bucket: static sources (長期：常用/不常用)
- 格式轉換
    - S*tream* - 即時轉換
        - MediaLive & MediaPackage
    - *ODV* - 隨時轉換 (配合lamda job定時)
        - MediaConvert
    - 格式：
    [HLS](https://en.wikipedia.org/wiki/HTTP_Live_Streaming)
    , CMAF
    , DASH ...
- 輸出方式
    - SDK - 夾一層自已backend，再落自己frontend
    - CloudFront/S3 - 直接提供，AWS website / 自己frontend

二家broadcast有既應該就係補聽同直播，分別係ODV同Stream
- S3 bucket = YouTube
- MediaLive = YouTube Live，將影片(input)轉成直播形式
- 建議Native AWS，維護較易，大部分安全性交比AWS做
- 片果D野 格式同用量果D panel大佬最熟，請教左佢地先評估到要可唔可行

---
# 參考資料

## Billing：

[Medialive](https://aws.amazon.com/tw/medialive/pricing/) \
[S3](https://aws.amazon.com/tw/s3/pricing/?nc=sn&loc=4) \
[Cloudfront](https://aws.amazon.com/tw/cloudfront/pricing/?nc=sn&loc=3) \
[Lambda](https://aws.amazon.com/tw/lambda/pricing/) - maybe optional \
[Cloudformation](https://aws.amazon.com/tw/cloudformation/pricing/) - optional

---

## 1. [Two Input options](https://aws.amazon.com/tw/events/taiwan/techblogs/articles-Live_Streaming/)

1. S3 bucket - HLS
2. OBS - Live

---

## 2. [Live Streaming](https://aws.amazon.com/tw/solutions/implementations/live-streaming-on-aws/)

1. with S3 bucket
2. with MediaPackage

---

## 3. [Batch-transcoding videos](https://docs.aws.amazon.com/AmazonS3/latest/userguide/tutorial-s3-batchops-lambda-mediaconvert-video.html)

- AWS MediaConvert, Lamda, S3 Batch Operations

---

## 4. [On Demand | ODV](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/on-demand-video.html)

---

### AWS Media Services
& [provided use cases](https://aws.amazon.com/tw/media-services)

---

## References
### [AWS Video Hosting](https://blog.vidizmo.com/aws-video-hosting)