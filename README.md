# HSR

Models trained by us.

## HSR_V2.5

Built upon V2 with some optimizations in dataset processing.  
Dataset: same as V2.  
Accuracy has been significantly improved, with stronger AA. But by design it can't handle very severe aliasing.
Sharpness is relatively high.
・Fast processing speed, slightly slower than V2_s  
・Excellent at removing compression artifacts, with higher accuracy than V2  
・With some fine-tuning, it performs well on both low-resolution and high-resolution material  
・Depth of field preservation is not as good as V2 and it may introduce noise and ringing around edges (These issues will be addressed in V3)

> 在V2的基础上做了诸多数据集处理上的优化  
数据集来源：与V2相同  
准确度有相当的提升，抗锯齿能力更强但设计上并不能处理比较严重的锯齿，**锐利度较高**  
・运算速度快，比V2_s略慢  
・对压缩痕迹的清理非常优秀，且比V2准确度高  
・经过一些微调，对低分辨率素材、高分辨率素材均有不错的效果  
・景深保留没有V2做得好，可能会在线条周围引入噪点、振铃！这些问题会在V3解决

## HSR_V2

A 2x super-resolution model for anime.  
Compared to V1, the cleanup of compression artifacts has been optimized, **with a slight improvement in line sharpness**.  
Dataset: Recent anime BDMVs \(primary\), hentai BDMVs / WEB-DLs.    
Preserves details and depth of field, and upscales text with relatively high accuracy.  
Not suitable for animes with very poor image quality or severe aliasing.  
[Comparisons](https://slow.pics/s/xCgRtL4t)

> 针对压缩瑕疵清理的动画2x超分辨率模型  
在V1的基础上对压缩痕迹的清理进行了优化，**并略微提高了线条锐度**  
数据集来源：近年的表番BDMV\(主要\)、里番的BDMV/WEB-DL  
保留细节，保留景深，较为准确地放大文字  
不适用于画质过差或者锯齿严重的动画  
[对比图](https://slow.pics/s/xCgRtL4t)：**源图像**对比**缩小后用模型重新放大**，AniSD和AnimeJaNai是两个我觉得不错并且锐度比较接近的模型，请放大后对比！

## HSR_V2_s
The standard V2 version uses the RealPLKSR, while this V2_s version uses the RealPLKSR small size (the same as V1).  
Its processing speed is much faster, at the cost of some fine details not being as good as V2 — in most cases their quality is similar, so please make a trade-off.  
・Fast processing speed  
・Slightly inferior quality compared to the standard V2 version, especially in dark-area details and complex scenes  
・Provides necessary anti-aliasing, but cannot compensate if the original animation’s linework is poor

> V2标准版本使用RealPLKSR架构，此V2_s版本使用RealPLKSR small架构(与V1相同)  
运算速度会快非常多，代价是一些细节没有V2的质量好——大部分场景下两者质量相近，请自行取舍  
・运算速度快  
・质量略逊于V2标准版本，尤其暗部细节、复杂画面  
・有必要的抗锯齿效果，但如果动画本身润线质量差则无能为力

## HSR_V1

A soft 2x super-resolution model for anime.  
Designed for animes that aren't of particularly poor image-quality — cleans up compression, performs mild anti-aliasing, preserves depth of field, and denoises flat areas.  
Dataset: Recent anime BDMVs, hentai BDMVs, and recent hentai WEB-DLs(1080p/720p).  
The dataset distinguishes between line art and flat areas, and only denoising was applied to the flat areas.  
It does not sharpen blurred lines (such as those caused by depth of field), but if the overall linework is soft, it applies a mild sharpening effect.  
The goal of this model is to handle compression artifacts on lines during rescaling without excessively increasing line sharpness, so the model is overall tuned for low sharpness.

> 低锐度的动画2x超分辨率模型  
用于处理画质不是非常差的源——清理压缩痕迹、一定强度的抗锯齿、保留景深、平面降噪  
数据集来源：近年的表番BDMV、里番BDMV、近年的里番WEB-DL(1080p/720p)  
数据集处理特定地分为了线条、平面部分，平面部分仅做了降噪处理，因而你可以通过遮罩选择应用线条部分  
不会锐化虚化的线条(例如景深)，但如果整体线条比较糊则会有低强度的锐化效果  
因为目标是在rescale时能够处理线条上的压缩痕迹，并且不会过度调整线条锐度，所以该模型总体是偏低锐度的
