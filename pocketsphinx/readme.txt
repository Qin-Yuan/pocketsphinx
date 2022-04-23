1、使用PocketSphinx功能包实现语音识别

（1）启动
roslaunch pocketsphinx robocup.launch
（2）显示识别结果
rostopic echo /recognizer/output

2、通过语音控制机器人（小海龟）

（1）roslaunch robot_voice voice_commands.launch
（2）rosrun robot_voice voice_teleop.py
（3）rosrun turtlesim turtlesim_node
（4）rostopic echo /recognizer/output

3、语音合成
测试 roscore
（1）rosrun sound_play soundplay_node.py
（2）rosrun sound_play say.py "Hello World."