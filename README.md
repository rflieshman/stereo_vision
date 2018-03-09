# Stereo Vision
Distance measurement using Stereo Vision. This project mesaures the distance of an object using opencv stereo vision and python.

## Installations and Setup:
Stereo Camera Rig:
 <p align="center">
  <img src="stereo_rig.jpg" width=600 height=400>
 </p>

 ``` bash
 # Add conda to python2 path:
 export PATH=~/anaconda2/bin:$PATH
 
 # Download opencv package (2.4.13):
 conda install -c dhaneshr opencv  
 
 # Install other dependencies:
 conda install progressbar
 conda install simplejson
 
 sudo add-apt-repository ppa:zarquon42/meshlab
 sudo apt-get update
 sudo apt-get install meshlab

 # Test Webcams:
 python show_webcams.py -h
 python show_webcams.py 0 1
 
 # Take images for calibration:
 python capture_chessboards -h
 python capture_chessboards.py --rows 6 --columns 9 --square-size 2.5 --calibration-folder calibration_files 0 1 50 calibration_images
 
 # Calibrate cameras using calibration_images:
 python calibrate_cameras.py -h
 python capture_chessboards.py --rows 6 --columns 9 --square-size 2.5 --calibration-folder calibration_files 0 1 50 calibration_images
 # Error Note: If we do not hold the chessboard as 6x9 style(horizontally) it will not be able to calibrate the vertically captured image

# Generate Stereo Images for Point Cloud
python stereo_image_generator.py --output_folder stereo_images --interval 5 0 1
python stereo_image_generator.py -h

# Tune Block Matching Algorithm
python tune_blockmatcher.py -h
python tune_blockmatcher.py --use_stereobm --bm_settings settings.json calibration_files stereo_images




```
