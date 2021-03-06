# 2020-ACM-MM-Supplementary
Simply using the image-based algorithm to process the frame sequence independently always leads the unstable
problems, shown in left part of animations. Our model takes the flicking frames as input and produces it’s coherent
version. Our results are on the **right part** while the compared results are on the **left part**.
<p align='center'>  
  <img src='imgs/Abstract/ColorConstancy.gif' width='440'/>  
  <img src='imgs/Abstract/InsDec.gif' width='440'/>
</p>

<p align='center'>
  <img src='imgs/Abstract/color.gif' width='440'/>
  <img src='imgs/Abstract/cycleGan.gif' width='440'/>
</p>

## Introduction
This is some source code and additional visualization examples of our TDMS-Net, *Temporal Denoising Masks Synthesis Network for Learning Blind Video Temporal Consistency*.

**Motivation of Our Work**

Simply using the image-based method to solve the video processing task frame-by-frame may always lead the temporal consistent problem. Given unstable pre-processed frames, solving the flickering problem is viewed as a temporal dimension denoise task. Our ternary temporal denoising mask synthesis network (TDMS-Net) is proposed to predict the motion mask, soft optical flow and the refining mask to construct our target frame. The TDMS-Net learns the temporal consistency from the original video and apply the learned temporal feature to reprocess the output frames of image-based method. The TDMS-Net is blind to the pre-process method. 

**Insight of Our Work**
1. We present the TDMS-Net, a three-stream temporal consistency learning network, which takes use of the flow, motion mask and refining mask to synthesize the high-quality and coherent frame sequence.
2. Our model is blind to the pre-processed method, in another words, each image-based translation methods can cast their results to the video level in our model.
3. The dual flow is used to teach our model to process the foreground area and background area separately. By this way the model can modify the pre-processed frames accurately while other methods solve the problem roughly.
4. A new metric based on the video tracking method is proposed to evaluate the enhancement effect of our model perceptual aspect and temporal aspect.
<p align='center'>  
  <img src='imgs/architechture.PNG' width='880'/>  
</p>

## results
More quantity results can be found in [results.xlsx](results).
<p align='center'>
  <img src='imgs/table1.PNG'/>  
</p>

<p align='center'>  
  <img src='imgs/table2.PNG'/>  
</p>

<p align='center'>  
  <img src='imgs/table3.PNG'/>  
</p>

## Comparsions with Pre-processed Video
Our results are on the **left part** while the compared results are on the **right part**.
The comparison between the results of TDMS-Net (left) and the pre-processed video (right). There are many flickering area in the pre-processed video. The TDMS-Net can take advantage of the temporal features to eliminate the unstable area
- WCT Sketch and WCT Antimonocromatismo
<p align='center'>  
  <img src='imgs/OurVSPro-Prec/OvPa.gif' width='440'/>  
  <img src='imgs/OurVSPro-Prec/OvPb.gif' width='440'/>
</p>

- CycleGAN Photo-to-Vangogh and Colorization
<p align='center'>
  <img src='imgs/OurVSPro-Prec/OvPc.gif' width='440'/>
  <img src='imgs/OurVSPro-Prec/OvPd.gif' width='440'/>
</p>

- HDRToning and DBL ExpertsA
<p align='center'>
  <img src='imgs/OurVSPro-Prec/OvPe.gif' width='440'/>
  <img src='imgs/OurVSPro-Prec/OvPf.gif' width='440'/>
</p>

## Comparsions with Bonneel et al. 
Our results are on the **left part** while the compared results are on the **right part**.
The comparison between the results of TDMS-Net (left) and the results of Bonneel et al. (right). The method proposed by Bonneel et al. solves the flickering problem at the cost of perceptual quality. Many content features (color, illumination, shapes of objects) are lost in their results.
- WCT Wave and WCT Candy
<p align='center'>  
  <img src='imgs/OurVSSig/OvSa.gif' width='440'/>  
  <img src='imgs/OurVSSig/OvSb.gif' width='440'/>
</p>

- Fast-neural-style Princess and CycleGAN Photo-to-Ukiyoe
<p align='center'>
  <img src='imgs/OurVSSig/OvSc.gif' width='440'/>
  <img src='imgs/OurVSSig/OvSd.gif' width='440'/>
</p>

- Fast-neural-style Udnie and Colorization
<p align='center'>
  <img src='imgs/OurVSSig/OvSe.gif' width='440'/>
  <img src='imgs/OurVSSig/OvSf.gif' width='440'/>
</p>

## Comparsions with Lai et al. 
Our results are on the **left part** while the compared results are on the **right part**.
The comparison between the results of TDMS-Net (left) and the results of Lai et al. (right). TDMS-Net is more effective to solve the flickering problem. There are some less obvious flickering area in the results of Lai et al. while TDMS-Net can suppress the flickering problem to a level that is not visible to the human eyes.
- Fast-neural-style Udnie and HDRToning
<p align='center'>  
  <img src='imgs/OurVSECCV/OvEa.gif' width='440'/>  
  <img src='imgs/OurVSECCV/OvEb.gif' width='440'/>
</p>

- HDRToning and WCT Feathers
<p align='center'>
  <img src='imgs/OurVSECCV/OvEc.gif' width='440'/>
  <img src='imgs/OurVSECCV/OvEd.gif' width='440'/>
</p>

- Intrinsic Shading and WCT Wave
<p align='center'>
  <img src='imgs/OurVSECCV/OvEe.gif' width='440'/>
  <img src='imgs/OurVSECCV/OvEf.gif' width='440'/>
</p>