# Computer Vision Algorithm for Suturing Skill Assessment
## Project description
Suturing training requires objective skill evaluation. Based on the simulator described in [^first_paper] and [^dissertation], we developed the 2-generation suturing simulator (shown in Fig. 1a) to assess suturing skills. During the suturing training, a subject is instructed to perform outside-in sutures from Region 1 to 12 on a radial pattern (See Fig. 1b).

![images(modified)](https://user-images.githubusercontent.com/59490151/188658567-7e6c8b6e-1a1d-4193-a881-6af3391c2493.png)

This web page focuses on the improved computer vision algorithm for Camera 2 (See Fig. 1c). Compared with the predecessor[^2017paper], the enhanced algorithm
1. Uses object-oriented programming (OOP).
2. Increases the computational speed by using multithreading.
3. Improves needle/thread detection accuracy by using background subtraction techniques.
4. Supports analyzing video files and real-time video streams.
5. Allows re-insertion at each region.

[^first_paper]:
    Singapogu, Ravikiran B., Tanmay Kavathekar, John F. Eidt, Richard E. Groff, and Timothy C. Burg. "A Novel Platform for Assessment of Surgical Suturing Skill: Preliminary Results." In MMVR, pp. 375-378. 2016.

[^dissertation]:
    Kil, Irfan. "Development and Preliminary Validation of Image-enabled Process Metrics for Assessment of Open Surgery Suturing Skill." PhD diss., Clemson University, 2019

[^2017paper]:
    Kil, Irfan, Anand Jagannathan, Ravikiran B. Singapogu, and Richard E. Groff. "Development of computer vision algorithm towards assessment of suturing skill." In 2017 IEEE EMBS International Conference on Biomedical & Health Informatics (BHI), pp. 29-32. IEEE, 2017.

## Video demo
To verify the algorithm performance, we create a synchronized video, which includes two video streams.
- The left video is from Camera 1 (shown in Fig. 1a).
- The right video, overlaid with the detection results, is from Camera 2 (shown in Fig. 1c).

https://user-images.githubusercontent.com/59490151/189790317-d4b3917f-5cf8-402d-adcd-add7cf1e520c.mp4

Within the right video, the algorithm outputs are visualized by three image patches (shown on the far right) and four circles drawn on the white fabric. 
- For the three image patches:
  - The top image patch demonstrates the needle (shown in magenta) and the thread (shown in yellow) recognized by the algorithm. 
  - The middle image patch shows the needle swept area[^2018paper].
  - The bottom image patch shows the needle sway length[^2018paper].
- For the four circles drawn on the white fabric:
  - The blue circle denotes the needle tip detected by the algorithm.
  - The red circle represents the needle-thread connection detected by the algorithm.
  - The black circle denotes the detected needle entry location.
  - The magenta circle represents the detected needle exit location.
  
Those algorithm outputs are then used to generate metrics for suturing skill evaluation. A detailed description of the metrics can be found within [^2018paper].

[^2018paper]:
    Kil, Irfan, Richard E. Groff, and Ravikiran B. Singapogu. "Surgical suturing with depth constraints: Image-based metrics to assess skill." In 2018 40th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pp. 4146-4149. IEEE, 2018.

## System requirements
This algorithm is written in C++. It requires the following software
- Visual Studio 2017 (version: 15.45)
- OpenCV 3.4.0 (with GPU support)
- CUDA 9.1

## Code access
Since the project is still in progress, this website doesn’t contain the code. If you are interested in it, please get in touch with jianxig@g.clemson.edu.

## Acknowledgment
This work was supported by the National Institutes of Health (NIH) grant number 5R01HL146843. Meanwhile, I want to show my deep appreciation to my advisors, Dr. Richard E. Groff and Dr. Ravikiran B. Singapogu, who helped me throughout the project. I would also like to thank Zhanhe Liu, Simar P. Singh, and Mehdi Shayan, who supported me and gave valuable suggestions during the project.

