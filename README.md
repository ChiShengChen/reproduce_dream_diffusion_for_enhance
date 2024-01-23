# reproduce_dream_diffusion_for_enhance
## [on-going]  
In this repository I reproduced Dream Diffusion paper in local ubuntu environment, try to pre-trained EEG representation and use author checkpoints to generate images.  

### paper:  https://arxiv.org/abs/2306.16934  
### official code:  https://github.com/bbaaii/DreamDiffusion  

- [x] pretraining on EEG data
- [ ] fineture the stable diffusion with pre-trained fMRI Encoder
- [ ] Generating Images with Trained Checkpoints




/pretrains
┣ 📂 models
┃   ┗ 📜 config.yaml
┃   ┗ 📜 v1-5-pruned.ckpt

┣ 📂 generation  
┃   ┗ 📜 checkpoint_best.pth 

┣ 📂 eeg_pretain
┃   ┗ 📜 checkpoint.pth  (pre-trained EEG encoder)

/datasets
┣ 📂 imageNet_images (subset of Imagenet)

┗  📜 block_splits_by_image_all.pth
┗  📜 block_splits_by_image_single.pth 
┗  📜 eeg_5_95_std.pth  

/code
┣ 📂 sc_mbm
┃   ┗ 📜 mae_for_eeg.py
┃   ┗ 📜 trainer.py
┃   ┗ 📜 utils.py

┣ 📂 dc_ldm
┃   ┗ 📜 ldm_for_eeg.py
┃   ┗ 📜 utils.py
┃   ┣ 📂 models
┃   ┃   ┗ (adopted from LDM)
┃   ┣ 📂 modules
┃   ┃   ┗ (adopted from LDM)

┗  📜 stageA1_eeg_pretrain.py   (main script for EEG pre-training)
┗  📜 eeg_ldm.py    (main script for fine-tuning stable diffusion)
┗  📜 gen_eval_eeg.py               (main script for generating images)

┗  📜 dataset.py                (functions for loading datasets)
┗  📜 eval_metrics.py           (functions for evaluation metrics)
┗  📜 config.py                 (configurations for the main scripts)



Ref:  
You can also find code to parse the eeg data here: https://github.com/bobergsatoko/reproduce-dream-diffusion/blob/main/Reproduce_DreamDiffusion.ipynb
https://github.com/bobergsatoko/reproduce-dream-diffusion/tree/main
