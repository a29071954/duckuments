# Lane following {#demo-lane-following status=beta}

This is the description of lane following demo.

<div class='requirements' markdown="1">

Requires: Wheels calibration completed. 

Requires: Camera calibration completed.

Requires: Joystick demo has been successfully launched. 

</div>

## Video of expected results {#demo-template-expected}

Demo video online. https://www.youtube.com/watch?v=6V3w66mF7w0

## Duckietown setup notes {#demo-template-duckietown-setup}

A duckietown with white and yellow lanes. No obstacles on the lane.

## Duckiebot setup notes {#demo-template-duckiebot-setup}

Make sure the camera is heading ahead. Tighten the screws if necessary. 

## Pre-flight checklist {#demo-template-pre-flight}

Check: turn on joystick. 

Check: Enough battery of the duckiebot. 

## Demo instructions {#demo-template-run}

Here, give step by step instructions to reproduce the demo.

Step 1: On duckiebot, in $DUCKIERTOWN_ROOT directory, run command:

    duckiebot $ make demo-lane-following
    
Wait a while so that everything has been launched. Press R1 to start autonomous lane following. Press L1 to switch to joystick control. Press X to start anti-instagram. 
Empirically speaking, no duckiebot will successfully run the demo for its first time. Parameter tuning is a must. The only two parameters that you can modify is the gain and trim. The parameter pair which makes your bot go straight will unlikely work for the lane following due to the current controller design. Facts show that a gain ranging from 0.5 to 0.9, as long as paired with a suitable trim, will all work on this demo. Start with your parameter pair obtained from wheel calibration. Increase gain for higher speed. Increase trim to horizontally move the bot to the center of the lane. Decrease will do the inverse. 

Step 2: On laptop, make sure ros enviroment has been activated, run command:

    laptop $ rviz

In rviz, two markerarrays /bhsf/duckiebot_visualizer/segment_list_markers and /bhsf/lane_pose_visualizer_node/lane_pose_markers can be visualized. The green arrow shall be in a reasonable direction. 

Step 3: On laptop, make sure ros enviroment has been activated, run command:

    laptop $ rqt
    
In rqt, the images can be visualized are /$(vehicle_name)/camera_node/image/compressed, /$(vehicle_name)/line_detector_node/image_with_lines, /bhsf/lane_filter_node/belief_img.


## Troubleshooting {#demo-template-troubleshooting}

Contact Yang Shaohui(ETHZ) via Slack if any trouble occurs. 


