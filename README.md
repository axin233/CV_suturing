# Computer Vision Algorithm for real-time needle detection
## Introduction
Suturing training requires sensor-embedded simulators for objective skill evaluation. Based on the simulator described in [^first_paper] and [^dissertation], we developed the 2-generation simulator (shown in Fig. 1 (a)) for surgical suturing skill assessment. 

<!--
![images(modified)](https://user-images.githubusercontent.com/59490151/188658567-7e6c8b6e-1a1d-4193-a881-6af3391c2493.png)
-->

<!--
![simulator_v1](https://github.com/axin233/CV_suturing/assets/59490151/b7791806-e726-49d3-9a31-88ad06ca79e3)
-->

<p align="center">
  <img width="661" height="373" src="https://github.com/axin233/CV_suturing/assets/59490151/b7791806-e726-49d3-9a31-88ad06ca79e3">
</p>

> Fig. 1. The improved suturing simulator: (a) Front view; (b) Top view of the membrane housing; (c) The internal structure of the membrane housing; (d) Surface condition; (e) Depth condition.

To complete an exercise on the improved simulator, a participant starts inserting the needle at the mark on Suture 1 (see Fig. 1(b)). The ideal needle pull-out location (see Fig. 1(b)) is on the same radius, such that the edge of the brown circle is in the middle between the mark and the pull-out location. The participant then proceeds to Suture 2, using the same procedure. The exercise is completed when all 12 sutures have been finished. To simulate the actual surgery, the simulator has two configurations: 
- Surface condition (see Fig. 1 (d)).
- Depth condition (see Fig. 1 (e)).

## Computer vision algorithm for real-time needle detection
Kil et al. [^dissertation] have proposed a computer vision algorithm for detecting needle motion, which verified that needle swept area, needle sway length, and needle tip path can be used to distinguish participants' skill levels. This algorithm, however, was designed for processing comparatively small video data. To allow the algorithm to process a large amount of video data, we re-designed the computer vision algorithm. 

Compared with the predecessor, the enhanced algorithm has the following improvements.
1. has fewer fault detections with the help of a reliable light source (see Fig. 1 (c)).
2. Uses object-oriented programming (OOP).
3. Increases the computational speed by using multithreading.
4. Improves needle/thread detection accuracy by using background subtraction techniques.
5. Supports analyzing video files and real-time video streams from Camera 1 (See Fig. 1 (c)).
6. Allows re-insertion at each region.

[^first_paper]:
    Singapogu, Ravikiran B., Tanmay Kavathekar, John F. Eidt, Richard E. Groff, and Timothy C. Burg. "A Novel Platform for Assessment of Surgical Suturing Skill: Preliminary Results." In MMVR, pp. 375-378. 2016.

[^dissertation]:
    Kil, Irfan. "Development and preliminary validation of image-enabled process metrics for assessment of open surgery suturing skill." PhD diss., Clemson University, 2019

<!--
[^2017paper]:
    Kil, Irfan, Anand Jagannathan, Ravikiran B. Singapogu, and Richard E. Groff. "Development of computer vision algorithm towards assessment of suturing skill." In 2017 IEEE EMBS International Conference on Biomedical & Health Informatics (BHI), pp. 29-32. IEEE, 2017.
-->

## Video demo
To verify the algorithm performance, we create a synchronized video, which includes two video streams.
- The left video is from Camera 2 (see Fig. 1 (a)).
- The right video, overlaid with the detection results, is from Camera 1 (see Fig. 1 (c)).

https://github.com/axin233/CV_suturing/assets/59490151/418894a6-7f8b-4073-8c82-47128028bd26

Within the right video, the algorithm outputs are visualized by image patches (shown on the far right) and circles drawn on the white fabric. 
- For the image patches:
  - The top image patch demonstrates the needle (shown in magenta) and the thread (shown in yellow) recognized by the algorithm. 
  - The middle image patch shows the needle swept area.
  - The bottom image patch shows the needle sway length.
- For the circles drawn on the white fabric:
  - The blue circle denotes the detected needle tip.
  - The red circle represents the detected needle-thread connection.
  - The black circle denotes the detected needle entry location.
  - The magenta circle represents the detected needle exit location.

<!--
[^2018paper]:
    Kil, Irfan, Richard E. Groff, and Ravikiran B. Singapogu. "Surgical suturing with depth constraints: Image-based metrics to assess skill." In 2018 40th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pp. 4146-4149. IEEE, 2018.
-->

## How does it work

Fig. 2 shows the code structure of the simulator software, which includes the data collection program, the computer vision algorithm, and the metric calculation program. Details can be found in [^my_dissertation].

[^my_dissertation]:
    Gao, Jianxin. "Computer vision algorithms for assessment of surgical suturing skill using hand and needle motion" PhD proposal (unpublished)

<!--
![suturing_code](https://github.com/axin233/CV_suturing/assets/59490151/67cffa56-e580-4c05-80fd-94fc891707e6)
-->

<p align="center">
  <img width="800" height="379" src="https://github.com/axin233/CV_suturing/assets/59490151/67cffa56-e580-4c05-80fd-94fc891707e6">
</p>

> Fig. 2. Code structure of the simulator software

## Related works
The algorithm detection results have been used in the following papers:
> Shayan, A. M., Singh, S., Gao, J., Groff, R. E., Bible, J., Eidt, J. F., ... & Singapogu, R. (2023). Measuring hand movement for suturing skill assessment: A simulation-based study. Surgery, 174(5), 1184-1192.

> Singh, S., Shayan, A. M., Gao, J., Bible, J., Groff, R. E., & Singapogu, R. (2023). Objective and automated quantification of instrument handling for open surgical suturing skill assessment: A simulation-based study. OJEMB. (unpublished)

More papers will be coming soon! :hugs:

## System requirements
This algorithm is written in C++. It requires the following software
- Visual Studio 2017 (version: 15.45)
- OpenCV 3.4.0 (with GPU support)
- CUDA 9.1

## Code access
Since some of our papers are still in progress, this website doesn’t contain the code. If you are interested in it, please email me at jianxig@g.clemson.edu. :smile:

## Acknowledgment
This work was supported by the National Institutes of Health (NIH) grant number 5R01HL146843. Meanwhile, I want to show my deep appreciation to my advisors, Dr. Richard E. Groff and Dr. Ravikiran B. Singapogu, who helped me throughout the project. I would also like to thank Zhanhe Liu, Simar P. Singh, and Mehdi Shayan, who supported me and gave valuable suggestions during the project.

