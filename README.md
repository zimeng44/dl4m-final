## Introduction:

Foley-Gen is a generative machine learning model that generates noval foley sounds in 7 categories: Dog Bark, Footstep, Gunshot, Typing on Keyboard, Moving Motor Vehicle, Rain, Sneeze Cough. Our training dataset consists of 5,496 sound clips from the UrbanSound8K, FSD50K, and BBC Sound Effects datasets.

## Usage:

### If you want to use our checkpoint: 

1. Download the checkpoint here: https://drive.google.com/file/d/1hLbUi0veQ1D-yYGTxF-3rCfrVSIpzd6_/view?usp=sharing

2. Unzip the checkpoint and put the 'checkpoint' folder at the root level of this project.

3. Run `python inference.py`
   
   (The number of sounds that will be generated for each category can be modified by running `python inference.py --number_of_synthesized_sound_per_class = <number>`. The default number is 1 per category.)

### If you want to train the models yourself:

1. Train VQ-VAE:
   `python train_vqvae.py`
   
2. Extract code/embedding from trained VQ-VAE:
   `python extract_code.py`
   
3. Train PixelSnail:
   `python train_pixelsnail.py`
    
4. Inference:
   `python inference.py`

   (The number of sounds that will be generated for each category can be modified by running `python inference.py --number_of_synthesized_sound_per_class = <number>`. The default number is 1 per category.)

The synthesized sound samples will be saved to `./synthesized`

## Caution: Inference needs GPU with memory larger than 50GB, otherwise, 'CUDA Out of Memory' error might occur. 

## Reference: 
This project is based on a baseline model https://github.com/DCASE2023-Task7-Foley-Sound-Synthesis/dcase2023_task7_baseline .
Other models used in this project include MERT, VQ-VAE and PixelSnail.
