# Computer Vision Algorithm for Suturing Skill Assessment
This is an improved version of the algorithm desscribed in the paper *Development of Computer Vision Algorithm towards Assessment of Suturing Skill*[^2017paper]. Compared with the original version, the improved algorithm
1. Uses Object-oriented programming (OOP).
2. Increases the computational speed by using multithreading.
3. Improves needle/thread detection accuracy by using background subtraction techniques.
4. Supports analyzing video files or real-time video stream.
5. Allows re-insertion at each suture.

[^2017paper]:
    Kil, Irfan, Anand Jagannathan, Ravikiran B. Singapogu, and Richard E. Groff. "Development of computer vision algorithm towards assessment of suturing skill." In 2017 IEEE EMBS International Conference on Biomedical & Health Informatics (BHI), pp. 29-32. IEEE, 2017.

## Video demo
To verify the algorithm perfromance, we create the following synchronized video, which combines two video streams
- The left video is from a webcam mounting in front of the suturing simulator.
- The right video, overlaid with the detection results, is from a camera inside the simulator.

Within the right video, the algorithm output is visualized by 3 image patches and 4 circles with different colors. 

https://user-images.githubusercontent.com/59490151/188332404-ed8098eb-9aae-45f4-a8cf-57a4e1a8ce5a.mp4

