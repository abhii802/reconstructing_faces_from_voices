# Reconstructing faces from voices

##### Implementation of [Reconstructing faces from voices](https://arxiv.org/abs/1905.10604) paper 
Yandong Wen, Rita Singh, and Bhiksha Raj \s
Machine Learning for Signal Processing Group \s
Carnegie Mellon University

## Requirements

This implementation is based on Python 3.7 and Pytorch 1.1. 

We recommend you use conda to install the dependencies. All the requirements are found in `requirements.txt`. Run the following command to create a new conda environment using all the dependencies. 

```
$ ./install.sh
```

After you run the above script, you need to activate the environment where all the packages had been installed. The environment is called `voice2face` and can be run by:

```
$ source activate voice2face
```

## Processed data

The following are the **processed** training data we used for this paper. Please feel free to download them. \s
Voice data (log mel-spectrograms): [google drive](https://drive.google.com/open?id=1T5Mv_7FC2ZfrjQu17Rn9E24IOgdii4tj) \s
Face data (aligned face images): [google drive](https://drive.google.com/open?id=1qmxGwW5_lNQbTqwW81yPObJ-S-n3rpXp) \s
Once downloaded, update variables `voice_dir` and `face_dir` with the corresponding paths. \s

### Configurations 

See `config.py` on how to change configurations. 

## Train
We provide pretrained models including a voice embedding network and a trained generator in `pretrained_models/`. Or you can train your own generator by running the training script
```
$ python gan_train.py
```
The trained model is `models/generator.pth`

## Test
We provide some examples of generated faces (in `data/example_data/`) using the model in `pretrained_model/`.
If you want to generate faces for your own voice recording, specify the *test_data* and *model_path* of generator variables in `config.py` and run
```
$ python gan_test.py
``` 

Results will be in `data/test_data/`. For each voice recording named `xxx.wav`, we generate a face image named `xxx.png`.
The file names of the voices and faces starting with A-E are validation or testing set, while those starting with F-Z are training set.

## Citation

	@article{wen2019reconstructing,
	  title={Reconstructing faces from voices},
	  author={Yandong Wen, Rita Singh, Bhiksha Raj},
	  journal={arXiv preprint arXiv:1905.10604},
	  year={2019}
	}

## License 

Check LICENSE.md. 

