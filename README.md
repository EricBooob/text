# Results sample
This file provide the segmentation results of three sample images, including  
1) CFT_0678_1024  
2) CFT_4469_1024  
3) CFT_4895_1024  

## Sturcure 
The file structure is shown as follows: 
```
cd sample&&tree
.
├── CFT_0678_1024
│   ├── CFT_0678_1024_gt.png
│   ├── CFT_0678_1024_ori.jpg
│   ├── CFT_0678_1024_output_erode_stack
│   │   ├── CFT_0678_1024_output0.png
│   │   ├── CFT_0678_1024_output1.png
│   │   ├── CFT_0678_1024_output2.png
│   │   ├── CFT_0678_1024_output3.png
│   │   ├── CFT_0678_1024_output4.png
│   │   └── CFT_0678_1024_outputens.png
│   ├── CFT_0678_1024_output_stack_without_erode
│   │   ├── CFT_0678_1024_output0.png
│   │   ├── CFT_0678_1024_output1.png
│   │   ├── CFT_0678_1024_output2.png
│   │   ├── CFT_0678_1024_output3.png
│   │   ├── CFT_0678_1024_output4.png
│   │   └── CFT_0678_1024_outputens.png
│   └── CFT_0678_1024_Unet.jpg
├── CFT_4469_1024
│   ├── CFT_4469_1024_gt.png
│   ├── CFT_4469_1024_ori.jpg
│   ├── CFT_4469_1024_output_erode_stack
│   │   ├── CFT_4469_1024_output0.png
│   │   ├── CFT_4469_1024_output1.png
│   │   ├── CFT_4469_1024_output2.png
│   │   ├── CFT_4469_1024_output3.png
│   │   ├── CFT_4469_1024_output4.png
│   │   └── CFT_4469_1024_outputens.png
│   ├── CFT_4469_1024_output_stack_without_erode
│   │   ├── CFT_4469_1024_output0.png
│   │   ├── CFT_4469_1024_output1.png
│   │   ├── CFT_4469_1024_output2.png
│   │   ├── CFT_4469_1024_output3.png
│   │   ├── CFT_4469_1024_output4.png
│   │   └── CFT_4469_1024_outputens.png
│   └── CFT_4469_1024_Unet.jpg
└── CFT_4895_1024
    ├── CFT_4895_1024_gt.png
    ├── CFT_4895_1024_ori.jpg
    ├── CFT_4895_1024_output_erode_stack
    │   ├── CFT_4895_1024_output0.png
    │   ├── CFT_4895_1024_output1.png
    │   ├── CFT_4895_1024_output2.png
    │   ├── CFT_4895_1024_output3.png
    │   ├── CFT_4895_1024_output4.png
    │   └── CFT_4895_1024_outputens.png
    ├── CFT_4895_1024_output_stack_without_erode
    │   ├── CFT_4895_1024_output0.png
    │   ├── CFT_4895_1024_output1.png
    │   ├── CFT_4895_1024_output2.png
    │   ├── CFT_4895_1024_output3.png
    │   ├── CFT_4895_1024_output4.png
    │   └── CFT_4895_1024_outputens.png
    └── CFT_4895_1024_Unet.jpg

9 directories, 45 files
```  
## Details
1) In this file, ```*ori.jpg``` and ```*gt.png``` denotes the original input image and corresponding groundtruth respectively.  
2) Meanwhile, ```*Unet.jpg``` denotes the prediction of traditional supervised Unet.  
3) The data under dir ```*_stack_without_erode``` is the results via resizing original Diffusion Model Unet (DMUnet) prediction (512*512) into the original image shape
4) The data under dir ```*_erode_stack``` is the results via cv2.erode(kernel_size=3) from ```3)```. PS: only the predicted masks are eroded.  
5) ```*i.png```(i in range (0:4)) is the masks of total 5 times DMUnet inference (1000 diffusion steps) on one input. Moreover, ```*ens.png``` is the fused&&threshold results of ```*i.png```
