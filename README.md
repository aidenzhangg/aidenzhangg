
<p align="center">
  <img src="header.svg" alt="Aiden Zhang | Computer Engineering at the University of Waterloo" width="100%" />
</p>

<h3>Hi I'm Aiden</h3>

<p>I'm a 1A Computer Engineering student at the University of Waterloo. I like building things that connect software with the physical world, especially robotics, computer vision, and tools people actually use.</p>

<p>
  <a href="mailto:a522zhan@uwaterloo.ca">a522zhan@uwaterloo.ca</a>
  &nbsp;·&nbsp;
  <a href="https://aidenzhang.vercel.app">aidenzhang.vercel.app</a>
  &nbsp;·&nbsp;
  Seeking Summer 2027 co-op opportunities
</p>

---
## Engineering Design Teams

### Waterloo Aerial Robotics Group (WARG)
**Autonomy Subteam** · `Python` · `ROS 2` · `MAVROS` · `py_trees`

Developing autonomous drone software focused on flight safety, telemetry, and multi-drone coordination.

- **[Multi-Drone Deconfliction · PR #251](https://github.com/UWARG/autonomy-monorepo/pull/251)**  
  Built flight-path conflict detection with sweep-and-prune optimization, validated with 19 unit tests.

- **[Behaviour Tree Telemetry · PR #180](https://github.com/UWARG/autonomy-monorepo/pull/180)**  
  Developed MAVLink STATUSTEXT reporting, reducing 29 behaviour-tree messages to one compact status update.

- **[Emergency ABORT System · PR #218](https://github.com/UWARG/autonomy-monorepo/pull/218)**  
  Implemented safety-prioritized mission interruption and emergency landing through MAVROS.

### WATonomous
**EVE Autonomous Vehicle · Perception** · `C++` · `ROS 2`

- **[Autonomous Robot Navigation](https://github.com/aidenzhangg/autonomous-robot-navigation)**  
  Built a four-node navigation pipeline combining LiDAR mapping, A* pathfinding, and a 10 Hz Pure Pursuit controller.

---

## Projects

### [Recall — AI Study Assistant](https://github.com/aidenzhangg/recall) (Currently Building)
`React` · `TypeScript` · `Java` · `Spring Boot` · `Supabase` 

An AI-powered Chrome extension that helps students learn through personalized practice and focus monitoring.

- Built a full-stack Chrome extension that turns notes and PDFs into 4 question types, flashcards and practice papers, backed by 96 automated tests (60 Node, 36 JUnit), using React, TypeScript, Supabase and a Java Spring Boot backend
- Kept the AI API key off the client entirely and capped usage at 200 requests per user per day via a Supabase Edge Function
- Secured all 4 database operations with PostgreSQL row-level security, parameterized SQL and 210,000-iteration PBKDF2 hashing
- Classified 4 attention states from 478 MediaPipe face landmarks using 0.2 yaw / 0.24 pitch thresholds and blink scores


### [Food Recognition & Nutritional Analysis](https://github.com/aidenzhangg/computer-vision-food-health-checker)
`Python` · `PyTorch` · `YOLO11` · `OpenCV`

Built a real-time computer vision system that detects food items and provides nutritional information.

- Achieved **98% mAP50** on 245 labeled images at approximately **13.5 FPS**.
- Integrated multi-object detection and text-to-speech accessibility features.

---
