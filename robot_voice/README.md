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

4、智能对话
（1）roslaunch robot_voice chat_recognizer.launch
（2）roslaunch robot_voice start_chat.launch

5、讯飞
APPID   91fec8ef
APISecret   YzA2ZGQyNzUwMTJhNzdjODI1MWJkODY3
APIKey  1919573e49466800d7d56082a5915491
（1）语音识别
/home/benny/benny/ROS/demo/qinyuan/src/robot_voice/Linux_voice/bin/iat_online_record_sample
运行该文件
（2）语音合成
roscore
rosrun robot_voice tts_subscribe
rostopic pub /voiceWords std_msgs/String "data: '你好，我是机器人'"
（3）语音助手
roscore
rosrun robot_voice iat_publish
rosrun robot_voice voice_assistant
rostopic pub /voiceWakeup std_msgs/String "data: 'any string'"
