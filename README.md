## Robot Package Template

This is a GitHub template. You can make your own copy by clicking the green "Use this template" button.

It is recommended that you keep the repo/package name the same, but if you do change it, ensure you do a "Find all" using your IDE (or the built-in GitHub IDE by hitting the `.` key) and rename all instances of `my_bot` to whatever your project's name is.

Note that each directory currently has at least one file in it to ensure that git tracks the files (and, consequently, that a fresh clone has direcctories present for CMake to find). These example files can be removed if required (and the directories can be removed if `CMakeLists.txt` is adjusted accordingly).


## Commands

* Run robot launch file
```bash
ros2 launch articubot_one launch_sim.launch.py world:=src/articubot_one/worlds/obstacles.world 
```

* Run Rviz2
```bash
rviz2 -d src/articubot_one/config/view_bot.rviz
```

* Run keyboard twist
``` bash
 ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/cmd_vel_joy
```

* Run twist mux (optional)
    * Add to launch file
```bash
ros2 run twist_mux twist_mux --ros-args --params-file ./src/articubot_one/config/twist_mux.yaml -r cmd_vel_out:=diff_cont/cmd_vel_unstamped
```

* Launch Localization 
```bash
ros2 launch articubot_one localization_launch.py map:=./my_map_save.yaml use_sim_time:=true
```

* Launch Navigation
```bash
ros2 launch articubot_one navigation_launch.py map:=./my_map_save.yaml use_sim_time:=true
```

