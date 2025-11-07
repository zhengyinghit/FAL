# FAL
Code for our paper "Fuzzy-aware Loss for Source-free Domain Adaptation in Visual Emotion Recognition"

## Prerequisites:
- python == 3.9.20
- pytorch == 2.4.0
- torchvision == 0.19.0
- numpy, scipy, sklearn, PIL, argparse

## Dataset:

Please manually download the datasets [Twitter I](https://qzyou.github.io/projects/sa-ds/), [Twitter II](https://onedrive.live.com/?redeem=aHR0cHM6Ly8xZHJ2Lm1zL3UvcyFBcURaYnBfaUltV3JocHBmb1Zqck04R3FLSVZ4NlE%5FZT1meVhFMXU&id=AB6522E29F6ED9A0%21101727&cid=AB6522E29F6ED9A0), [Instagram](https://mm.doshisha.ac.jp/2016/12/01/image-sentiment-analysis-ja/), [Flickr](https://mm.doshisha.ac.jp/2016/12/01/image-sentiment-analysis-ja/), [FI](https://qzyou.github.io/projects/sa-ds/), [EmoSet](https://vcc.tech/EmoSet), [Office-Home](https://www.hemanthdv.org/officeHomeDataset.html) from the official websites, and modify the path of images in each '.txt' under the folder './data/'.

## Training:

- Train model on the source domain
    ```python
    python image_source.py --trte val --output ckps/source/ --gpu_id 0 --dset sentiment --max_epoch 10 --s 0 
    ```
	
- Adaptation to other target domains
    ```python
    python image_target.py --dset sentiment --gpu_id 0 --s 0 --max_epoch 5 --interval 5 --output_src ckps/source/ --output ckps/fal/
    ```

## Citation

If you find this code useful for your research, please cite our paper.
```
@article{zheng2025fuzzy,
  title={Fuzzy-aware Loss for Source-free Domain Adaptation in Visual Emotion Recognition},
  author={Zheng, Ying and Zhang, Yiyi and Wang, Yi and Chau, Lap-Pui},
  journal={arXiv:2501.15519},
  year={2025}
}
```

## Acknowledgment

This project is based on SHOT ([paper](https://proceedings.mlr.press/v119/liang20a.html), [code](https://github.com/tim-learn/SHOT)), thanks for their excellent works.

## Contact
If you have any questions or suggestions, please contact zhengyinghit@outlook.com. Thanks for your attention!
