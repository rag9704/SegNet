# Tensorflow-SegNet
Implement slightly different (see below for detail) [SegNet](http://arxiv.org/abs/1511.00561) in tensorflow,
successfully trained segnet-basic in CamVid dataset.






# Requirement
tensorflow 1.0
Pillow (optional, for write label image)
scikit-image


# Usage
see also example.sh
training:

  python main.py --log_dir=path_to_your_log --image_dir=path_to_CamVid_train.txt --val_dir=path_to_CamVid_val.txt --batch_size=5

finetune:

  python main.py --finetune=path_to_saved_ckpt --log_dir=path_to_your_log --image_dir=path_to_CamVid_train.txt --val_dir=path_to_CamVid_val.txt --batch_size=5

testing:

  python main.py --testing=path_to_saved_ckpt --log_dir=path_to_your_log --test_dir=path_to_CamVid_train.txt --batch_size=5 --save_image=True

You can set default path and parameters in main.py line 6~18.
note: in --testing you can specify whether to save predicted images, currently only save one image
for manually checking, will be configured to be more flexible.

# Dataset
This Implement default to use CamVid dataset as described in the original SegNet paper,
The dataset can be download from author's github https://github.com/alexgkendall/SegNet-Tutorial in the CamVid folder

example format:

"path_to_image1" "path_to_corresponded_label_image1",

"path_to_image2" "path_to_corresponded_label_image2",

"path_to_image3" "path_to_corresponded_label_image3",

.......
