---
layout: project
title: About My Project
permalink: /about-my-project.html

subtitle: Human Arm vs Robotic Arm Lego Build
project_title: Developing Edge AI Applications for Human-Robot Collaboration in LEGO Assembling Operations

problem: |

  As Artificial Intelligence continues to move beyond the screen, one major question is: Can AI help robots interact with physical objects and assist humans in real-world assembly tasks? This project explores that question through LEGO assembly. LEGO pieces are small, lightweight, and safe to test with, but they also create real engineering challenges because they vary in shape, size, color, height, and orientation. These challenges make LEGO pieces a useful small-scale model for larger applications in construction, manufacturing, and automated assembly. Our research focuses on how Edge AI, computer vision, and robotics can work together to help a robotic arm detect LEGO pieces, understand their location, and support human-robot collaboration during assembly operations. This is especially important because some users, including children, elderly individuals, and individuals with disabilities, may need assistance with locating, selecting, or assembling small pieces.


approach: |
 This project developed an Edge AI and robotic vision pipeline for LEGO assembly using YOLO-based object detection, camera-based scaling, and a WidowX-250 S 6DOF robotic arm.

  Tools and systems used in this project include:
  - Python as the main programming language
  - NumPy and OpenCV for image processing and computer vision
  - Ultralytics YOLO models for LEGO object detection
  - A LEGO dataset containing approximately 200 labeled part classes
  - A selective subset of common LEGO pieces for hardware testing
  - NVIDIA Jetson Developer Kits for Edge AI deployment
  - Webcam/camera sensor for visual input
  - QR-code reference points for camera scaling and pixel-to-millimeter conversion
  - Transformation matrices for converting image coordinates into real-world measurements
  - ROS 2 for robot communication, control, and simulation
  - Trossen Robotics WidowX-250 S 6DOF robotic arm as the prototype testing platform
  - Mendeley Desktop for organizing research sources, citations, and references

  Our approach began with training and evaluating multiple YOLO model variations using performance metrics such as precision, recall, F1 score, Intersection over Union (IoU), and mean Average Precision (mAP). These metrics helped us compare model performance beyond visual results and determine which model would be most practical for robotic deployment. A major challenge was that many of the top-detected LEGO classes from the full dataset were not physically available for robot testing. Because of this, we created a selective subset of common LEGO pieces, including pieces such as 1x1, 1x2, 1x4, 2x2, and 2x4 bricks. This allowed us to continue testing the detection-to-robot pipeline while staying realistic with the pieces we actually had. The robotic portion of the project focused on connecting detection to physical movement. A QR code was used as a reference object to help define the camera's coordinate frame, correct image perspective, and calculate the pixel-to-millimeter scale. This step was important because the robot cannot move based on image pixels alone; the system must convert camera detections into real-world measurements before the robot arm can pick up a LEGO piece. Once the camera detected the QR code as it's refernce point we would then send our best.pt file for our computer vision YOLO model to a NVIDIA Jetson computer. Whith now the YOLO model, robot arm, camera, and 500 lines of code for robotic movements we are now able to get our robot to detect,pick up, and drop LEGO pieces.


outcome: |
  Research Outcome : The final research outcome was a technical research paper and symposium presentation that explained the development process, model evaluation, literature review, research gaps, limitations, unexpected findings, and future improvements for human-robot collaborative LEGO assembly.
  Through this project, we learned that successful robotic assembly requires more than object detection. The system must also identify the correct LEGO class, calculate object position and orientation, convert image pixels into real-world measurements, and prepare robot-ready coordinates for movement.
  One unexpected finding was that some P2-architecture YOLO variants did not perform as strongly as expected, even though they are often associated with small-object detection. This showed us that model success depends on more than object size alone. Dataset quality, image scale, class similarity, training conditions, and deployment hardware all affect performance.
  
  Prototype Outcome :The prototype goal was to build a vision-guided robotic system that could detect LEGO pieces, calculate their position, and support pick-and-place operations using the WidowX-250 S robotic arm. The project helped build the foundation for connecting YOLO object detection, QR-code scaling, Edge AI deployment, ROS 2 control, and robotic manipulation. Limitations included the use of a selective LEGO subset for hardware testing, confusion between visually similar LEGO classes, difficulty distinguishing pieces with the same row-and-column layout but different heights, and computational limits when deploying larger YOLO models on NVIDIA Jetson hardware. Future improvements include training YOLO models with more multi-angle images, improving height recognition for similar LEGO pieces, updating robot code so the arm can apply controlled pressure when connecting LEGO bricks, expanding LEGO assembly simulation, and testing the system with additional LEGO datasets to improve generalization.
  
final_report_url: 
  <iframe
  src = "/assets/pdfs/P2___SAIRI_Final_Paper.pdf"
  width = "100%"
  height = "700px">
  </iframe>
  <p>
  <a href="/assets/pdfs/P2___SAIRI_Final_Paper.pdf" target="_blank">
    Open Final Research Paper PDF
  </a>
  </p>
  

grad_mentor:
  name: Derrick Mirindi
  linkedin: https://www.linkedin.com/in/derrick-mirindi-18b538b8/

faculty_mentor:
  name: Dr. Yuhan Jiang
  linkedin: https://www.linkedin.com/in/yuhan-jiang-aa9097b9/
---
