
<p align="center">
  <img src="header.svg" alt="Aiden Zhang | Computer Engineering at the University of Waterloo" width="100%" />
</p>

<h3>Hey, I'm Aiden.</h3>

<p>I'm a 1A Computer Engineering student at the University of Waterloo. I like building things that connect software with the physical world, especially robotics, computer vision, and tools people actually use.</p>

<p>
  <a href="mailto:a522zhan@uwaterloo.ca">a522zhan@uwaterloo.ca</a>
  &nbsp;·&nbsp;
  <a href="https://aidenzhang.vercel.app">aidenzhang.vercel.app</a>
  &nbsp;·&nbsp;
  Seeking Summer 2027 co-op opportunities
</p>

---

<h3>Engineering Design Teams</h3>

<table>
<tr>
<td width="50%" valign="top">

<h4>Waterloo Aerial Robotics Group</h4>

<sub><b>WARG · Autonomy Subteam</b></sub>

<p>Building software for autonomous drone operations, including behaviour-tree telemetry, emergency flight safety, and multi-agent coordination.</p>

<b>WARG Autonomy contributions</b>

<p>
  <b>Multi-Drone Deconfliction</b>
  <a href="https://github.com/UWARG/autonomy-monorepo/pull/251">[PR #251]</a> (in review)
</p>

<p>Built a conflict-detection module that checks every drone's planned flight path against every other drone's and reports any place two of them come closer than a minimum separation distance. It catches crossings, near misses, overlaps along shared region boundaries, and drones hovering in another's path. Each conflict reports which drones and flight legs are involved, the closest point on each leg, and the distance between them.</p>

<ul>
  <li>Two implementations: brute force, O(S²), and sweep and prune, O(S log S + C), which skips drones that are far apart</li>
  <li>Cross-checked on 200 random multi-drone scenarios, where both implementations must find the same conflicts</li>
  <li>19 unit tests covering crossing, touching, collinear overlap and near-miss cases</li>
  <li>Added a shared <code>PathConflict</code> type so other modules can act on the results</li>
</ul>

<p>
  <b>Behaviour Tree Telemetry</b>
  <a href="https://github.com/UWARG/autonomy-monorepo/pull/180">[PR #180]</a>
</p>

<p>Built a ROS 2 node that reports which step of the drone's behaviour tree is running over MAVLink STATUSTEXT, the same radio link the pilots use. The tree is numbered and saved to a file before takeoff, so in flight only the running node's number is sent, and a pymavlink ground tool redraws the whole tree from it. The team can follow the mission without an LTE connection.</p>

<ul>
  <li>Cut each update from 29 messages (one per node of the mission tree) to a single 3–4 character message, such as <code>S,17</code></li>
  <li>Reads the tree's state every 0.5 s, sends on every change, and repeats every 30 s for ground stations that connect late</li>
  <li>Retries every 2 s until the mission engine is up, so startup order doesn't matter</li>
</ul>

<p>
  <b>Emergency ABORT System</b>
  <a href="https://github.com/UWARG/autonomy-monorepo/pull/218">[PR #218]</a>
</p>

<p>Added a safety check that runs before the mission on every tick of the behaviour tree. When the ground station sends ABORT, it stops the active mission and commands an immediate landing through MAVROS, even while the mission is paused by the kill switch.</p>

<ul>
  <li>Checked at the start of every 500 ms tick, so the mission stops within one tick of the command arriving</li>
  <li>Retries the land command until the flight controller accepts it, and never resumes the mission afterward</li>
  <li>Tested in Docker: ABORT stopped the mission and handed control to the landing behaviour</li>
</ul>

</td>
<td width="50%" valign="top">

<h4>WATonomous</h4>

<sub><b>EVE Autonomous Vehicle · Perception</b></sub>

<p>Working on autonomous vehicle perception, multi-object tracking, and robotic navigation using ROS 2.</p>

<b>Currently working on</b>

<p>
  <a href="https://github.com/WATonomous/wato_monorepo/issues/583"><b>PERCEPTION: Tracking Changes #583</b></a>
</p>

<p>Investigating alternative multi-object tracking algorithms for 3D object detection. Starting by evaluating the existing ByteTrack implementation, analyzing its accuracy, and comparing other tracking approaches for compatibility and performance.</p>

<b>Previous work</b>

<p><b>Autonomous Robot Navigation</b></p>

<p>Developed a four-node C++ and ROS 2 navigation pipeline combining LiDAR mapping, odometry, A* pathfinding, and Pure Pursuit control.</p>

<p><b>Obstacle-Aware Planning</b></p>

<p>Implemented occupancy-grid mapping with obstacle inflation and eight-direction path planning to generate collision-aware routes.</p>


</td>
</tr>
</table>

---

## Currently Building

<table>
<tr>
<td width="50%" valign="top">

### [Recall — AI Study Assistant](YOUR_RECALL_REPO_URL)

<sub>Java · Spring Boot · React · TypeScript · PostgreSQL · ML</sub>

<br/><br/>

Building a Chrome extension that helps students learn from their own course materials through personalized practice, adaptive learning, and study tools.

- Built a Chrome side panel with interactive quizzes, hints, retries, and saved progress.
- Developing adaptive quizzes that revisit weak topics and generate targeted practice questions based on previous mistakes.
- Exploring **OpenCV and gaze estimation** to identify possible distractions and offer gentle check-ins or break reminders.
- Planning flashcards, practice tests from uploaded past exams, and learning-resource recommendations.

<br/>

<sub>In development</sub>

</td>
<td width="50%" valign="top">

### Recall Connect — Phone-to-PC Sharing

<sub>Windows · Cross-Device Communication · File Transfer</sub>

<br/><br/>

Building a companion tool for Recall that makes it easier to transfer handwritten notes, textbook pages, and lecture photos from a phone directly to a Windows laptop.

- Exploring a workflow to send photos directly from a phone's Share menu to a Windows laptop.
- Investigating direct device-to-device transfer without requiring manual cloud uploads.
- Planning integration with Recall so transferred photos can be imported as study materials for personalized quizzes and flashcards.

<br/>

<sub>In development · Device transfer and Recall integration are planned.</sub>

</td>
</tr>
</table>




---

<h3>Projects</h3>

<table>
<tr>
<td width="50%" valign="top">

<h4>
  <a href="https://github.com/aidenzhangg/computer-vision-food-health-checker">Food Recognition &amp; Nutritional Analysis</a>
</h4>

<sub><b>Python · PyTorch · OpenCV · YOLO11</b></sub>

<p>A computer vision application that identifies food items in real time and provides nutritional feedback.</p>

<p>Started with a TensorFlow CNN classifier before upgrading to a fine-tuned YOLO11 detection model. Collected and manually labelled training images, trained the model, and integrated it with an OpenCV webcam pipeline.</p>

<p>The final system detects multiple food items simultaneously, displaying bounding boxes, predicted categories, and confidence scores.</p>

<b>Results</b>

<ul>
<li><b>245</b> manually labelled images</li>
<li><b>98% mAP50</b> validation performance</li>
<li><b>~13.5 FPS</b> across 300 webcam frames</li>
<li><b>5</b> supported food categories</li>
<li><b>96%</b> original CNN test accuracy</li>
</ul>


<a href="https://github.com/aidenzhangg/computer-vision-food-health-checker">View Source Code</a>

</td>
<td width="50%" valign="top">

<h4>Drone Behaviour Tree Telemetry</h4>

<sub><b>ROS 2 · MAVLink · MAVROS · ArduPilot SITL</b></sub>

<p>Developed a telemetry system for WARG that communicates autonomous drone behaviour states to ground operators.</p>

<p>The system reads live ROS 2 behaviour-tree snapshots, maps behaviours to compact identifiers, and transmits the active state through MAVLink STATUSTEXT messages.</p>

<p>Designed to provide autonomy visibility even when LTE connectivity is unavailable, while minimizing communication overhead.</p>

<b>Technical highlights</b>

<ul>
<li>Compact messages targeting <b>50 bytes or less</b></li>
<li>Event-driven state updates</li>
<li><b>30-second</b> periodic retransmission</li>
<li>Automated behaviour-to-ID mapping</li>
<li>Parent-child behaviour tracking</li>
<li>Validated <b>4 autonomy states</b> through Docker, ArduPilot SITL, MAVROS, and Mission Planner</li>
</ul>

<a href="https://github.com/UWARG/autonomy-monorepo/pull/218">View PR #218</a>

</td>
</tr>

<tr>
<td width="50%" valign="top">

<h4>Drone Emergency ABORT System</h4>

<sub><b>Flight Safety · ROS 2 · Behaviour Trees</b></sub>

<p>Developed an emergency flight-safety mechanism for WARG's autonomous drone system.</p>

<p>Implemented ABORT handling within a ROS 2 behaviour-tree architecture, allowing a safety command to interrupt the current mission and trigger an immediate landing through MAVROS.</p>

<p>The system prioritizes emergency commands over normal autonomous behaviour to support predictable responses during unsafe flight conditions.</p>

<b>Technical highlights</b>

<ul>
<li>Emergency behaviour-tree interruption</li>
<li>Immediate landing through MAVROS</li>
<li>ROS 2 and py_trees integration</li>
<li>Safety-prioritized mission execution</li>
</ul>

<a href="https://github.com/UWARG/autonomy-monorepo/pull/180">View PR #180</a>

</td>
<td width="50%" valign="top">

<h4>
  <a href="https://github.com/aidenzhangg/autonomous-robot-navigation">Autonomous Robot Navigation &amp; LiDAR Mapping</a>
</h4>

<sub><b>C++ · ROS 2 · LiDAR · Path Planning</b></sub>

<p>Built a four-node autonomous navigation system combining LiDAR perception, occupancy mapping, route planning, and motion control.</p>

<p>The system processes LiDAR measurements, generates obstacle-aware occupancy grids, computes routes using A*, and follows paths through a Pure Pursuit controller.</p>

<b>Technical highlights</b>

<ul>
<li><b>100 × 100 m</b> occupancy grid</li>
<li><b>0.1 m</b> mapping resolution</li>
<li><b>0.65 m</b> obstacle inflation</li>
<li><b>8-direction A*</b> path planning</li>
<li><b>10 Hz</b> Pure Pursuit controller</li>
<li>Odometry integration and ROS 2 communication</li>
</ul>

<a href="https://github.com/aidenzhangg/autonomous-robot-navigation">View Source Code</a>

</td>
</tr>
</table>
