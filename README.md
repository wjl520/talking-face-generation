# Talking-Face-Generation
  The purpose of this repo is to make notes for talking face/head generation.

## Methods
  The methods can divide into real-time and offline. Generating talking face in real-time is our goal, therefore we only discuss nearly real-time methods.
* 2D-based methods
   * audio+image --> landmark --> GAN model --> face generation
   * ref：https://github.com/YuanxunLu/LiveSpeechPortraits
   
* 3D-based methods
    * images --> 3D render and landmark --> GAN model --> face generation
    * audio --> extract audio feature --> high-level feature
    
* NeRF-based methods (non real-time)

## Datasets
  * (1) Chinese
     * News video from CCTV (https://news.cctv.com/)
     * record video by your phone.
  * (2) English
     * mostly obtained by youtube.
     
## Preprocess
  * (1) Chinese audio: 
    * ffmpeg extract audio file, mainly xx.wav file, the sample rate usually is 16k. the code is `ffmpeg -y -i xx.mp4 -async 1 -ac 1 -vn -acodec pcm_s16le -ar 16000 xx.wav`
    * the pretrained model (such as deepspeech) extract the high-level audio feature; or MFCC directly extract audio file, and mfcc features are obtained.
    
  * (2) video: 
    *　detect and crop face, ffmpeg tool extracts image set in 25 fps.
    * `ffmpeg -y -i xx.mp4 -r 25 ./img/`
## 
