# talking-face-generation
  The purpose of this repo is to make notes for talking face/head generation.

# Methods
  This methods can divide into real-time and offline. Generating talking face in real-time is our goal, therefore we only discuss nearly real-time methods.
1. 2D-based methods
   * audio+image --> landmark --> GAN model --> face generation
   * ref：https://github.com/YuanxunLu/LiveSpeechPortraits
   
2. 3D-based methods
    images --> 3D render and landmark --> GAN model --> face generation
    audio --> extract audio feature --> high-level feature
    
4. NeRF-based methods

# Datasets
one video clip or multiple videos for training.
# Preprocess
  (1) audio: deepspeech or mfcc, 16k sample rate.
    
  (2) video: detect and crop face, ffmpeg tool extracts image set in 25 fps.
    video_path = "./xx.mp4"
    save_path = "./ori_img/"
    if not os.path.exists(save_path):
      os.makedirs(save_path)
    "ffmpeg -y -i {} -r 25 {}".format(video_path, save_path)
