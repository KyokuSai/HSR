# HSR

Models trained by us.

## HSR_V1

A soft 2x super-resolution model for anime.  
Designed for animes that aren't of particularly poor image-quality — cleans up compression, performs mild anti-aliasing, preserves depth of field, and denoises flat areas.  
Dataset: Recent anime BDMVs, hentai BDMVs, and recent hentai WEB-DLs(1080p/720p).  
The dataset distinguishes between line art and flat areas, and only denoising was applied to the flat areas.  
It does not sharpen blurred lines (such as those caused by depth of field), but if the overall linework is soft, it applies a mild sharpening effect.  
The goal of this model is to handle compression artifacts on lines during rescaling without excessively increasing line sharpness, so the model is overall tuned for low sharpness.

***

低锐度的动画2x超分辨率模型  
用于处理画质不是非常差的源——清理压缩痕迹、一定强度的抗锯齿、保留景深、平面降噪  
数据集来源：近年的表番BDMV、里番BDMV、近年的里番WEB-DL(1080p/720p)  
数据集处理特定地分为了线条、平面部分，平面部分仅做了降噪处理，因而你可以通过遮罩选择应用线条部分  
不会锐化虚化的线条(例如景深)，但如果整体线条比较糊则会有低强度的锐化效果  
因为目标是在rescale时能够处理线条上的压缩痕迹，并且不会过度调整线条锐度，所以该模型总体是偏低锐度的
