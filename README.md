# Computer Vision Algorithm for Suturing Skill Assessment
## Project description
Suturing training requires objective skill evaluation. Based on the simulator described in [^dissertation] and [^2017paper], we develop the 2-generation of the suturing simulator (shown in Fig. ). During the suturing training, a subject is required to perform outside-in sutures from Region 1 to 12 on a radial pattern (See Fig. ).

This web page focuses on the improved computer vision algorithm for the camera inside the simulator (See Fig. ). Compared with the predecessor[^2017paper], the improved version
1. Uses object-oriented programming (OOP).
2. Increases the computational speed by using multithreading.
3. Improves needle/thread detection accuracy by using background subtraction techniques.
4. Supports analyzing video files and real-time video stream.
5. Allows re-insertion at each region.

[^dissertation]:
    Kil, Irfan. "Development and Preliminary Validation of Image-enabled Process Metrics for Assessment of Open Surgery Suturing Skill." PhD diss., Clemson University, 2019

[^2017paper]:
    Kil, Irfan, Anand Jagannathan, Ravikiran B. Singapogu, and Richard E. Groff. "Development of computer vision algorithm towards assessment of suturing skill." In 2017 IEEE EMBS International Conference on Biomedical & Health Informatics (BHI), pp. 29-32. IEEE, 2017.

## Video demo
To verify the algorithm perfromance, we create a synchronized video, which includes two video streams.
- The left video is from a webcam mounting in front of the suturing simulator.
- The right video, overlaid with the detection results, is from a camera inside the simulator.

https://user-images.githubusercontent.com/59490151/188332404-ed8098eb-9aae-45f4-a8cf-57a4e1a8ce5a.mp4

Within the right video, the algorithm output is visualized by 3 image patches (shown on the far right) and 4 circles drawn on the white fabric. 
- For the 3 image patches:
  - The top image patch demonstrates the needle (shown in magenta) and the thread (shown in yellow) that recognized by the algorithm. 
  - The middle image patch shows the needle swept area[^2018paper].
  - The bottom image patch shows the needle sway length[^2018paper].
- For the 4 circles drawn on the white fabric:
  - The blue circle denotes the needle tip detected by the algorithm.
  - The red circle represents the needle-thread connection detected by the algorithm.
  - The black circle denotes the detected needle entry location.
  - The magenta circle represents the detected needle exit location.
  
Those algorithm output is then used to generate metrics for suturing skill evaluation. The detailed description of the metrics can be found within the paper *Surgical Suturing with Depth Constraints: Image-based Metrics to Assess Skill*[^2018paper].

[^2018paper]:
    Kil, Irfan, Richard E. Groff, and Ravikiran B. Singapogu. "Surgical suturing with depth constraints: Image-based metrics to assess skill." In 2018 40th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pp. 4146-4149. IEEE, 2018.

## System requirements
This algorithm is written in C++. It requires the following software
- Visual Studio 2017 (version: 15.45)
- OpenCV 3.4.0 (with GPU support)
- CUDA 9.1

