# TAG Model Zoo

## Introduction

This file documents a collection of TAG models reported in our paper.

#### How to Read the Tables
* The "Name" column contains a link to the config file. 
*  Note that ”l” and ”h” represent layer number and head dimension of M3 Transformers, respectively. "Top" denotes the number of proposals used for keypoint sampling from RPN stage. ”Rel. Trans.” and ”Rep. and Scal. Trans.” refer to mutual-relation trans-former, and multi-representation and multi- scale transformer, respectively. "mAP" represents 3D mean average precision (mAP) on LEVEL_1 difficulty in the Vehicle class with IoU threshold of 0.7 on the full 202 Waymo Validation Set.

## ST-VQA Dataset Model Zoo

<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Name</th>
<th valign="bottom">val Acc.</th>
<th valign="bottom">val Val ANLS</th>
<th valign="bottom">Test Val ANLS</th>
<th valign="bottom">download</th>
 <tr><td align="left"><a href="https://github.com/HenryJunW/TAG/blob/main/save/exp_yaml/stvqa_TAG_inference.yaml">TAG</a></td>
<td align="center">NA</td>
<td align="center">NA</td>
<td align="center">NA</td>
<td align="center"><a href="https://drive.google.com/file/d/1gwDXXo6LYCSaCo1B7r3fbu7j504Vw-Xj/view?usp=sharing">model</a></td>
</tr>

 <tr><td align="left"><a href="https://github.com/HenryJunW/TAG/blob/main/save/exp_yaml/stvqa_m4c_plus_w_tag_textvqa.yaml">stvqa_M4C_TAG_w_textvqa</a></td>
<td align="center">48.69</td>
<td align="center">0.579</td>
<td align="center">0.571</td>
<td align="center"><a href="https://drive.google.com/file/d/1EeBXWOAJcXa0k7UF1O8C7itVqVgjLGp7/view?usp=sharing">model</a></td>
</tr>

 <tr><td align="left"><a href="https://github.com/HenryJunW/TAG/blob/main/save/exp_yaml/stvqa_tap_refine_w_tag_textvqa.yaml">stvqa_TAP_TAG_w_textvqa</a></td>
<td align="center">53.53</td>
<td align="center">0.620</td>
<td align="center">0.602</td>
<td align="center"><a href="https://drive.google.com/file/d/1Fg2KjtHSyuXf8fEkr7l8qYv-4Me5XRot/view?usp=sharing">model</a></td>
</tr>

</tbody></table>
