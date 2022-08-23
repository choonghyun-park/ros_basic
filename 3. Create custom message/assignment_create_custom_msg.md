# Assignemtn of create custom message
Custom message를 정의하고, publish하는 과제입니다.\
과제 내용은 beginner_tutorials에서 아래 메시지 포멧으로 현재 시간 정보를 담은 메시지를 publish 하는 것입니다.\
Time.msg :
```
Header header
int32 hour
int32 minute
int32 second
string whole_time
```

## Description
예시 :
* 현재 시간이 14시 11분 56초인 경우 :
hour = 14
minute = 11
second = 56
whole_time = "12:11:56"
* 현재 시간이 02시 18분 07초인 경우 :
hour = 02
minute = 18
second = 07
whole_time = "02:18:07"

위와 같은 포멧으로 publish 해주시면 됩니다!

## Submission
1. rostopic echo로 custom message를 실시간으로 출력하는 동영상
2. 출력에 사용한 python source code (예 : time_publisher.py)
3. Time.msg
![Screenshot from 2022-07-21 19-49-40](https://user-images.githubusercontent.com/78340346/180196688-be6584b0-fdf4-41c5-be80-c378db34dbe6.png)
