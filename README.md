
# 타임랩스 만들기 

[실시간 시계](https://ko.wikipedia.org/wiki/%EC%8B%A4%EC%8B%9C%EA%B0%84_%EC%8B%9C%EA%B3%84)의 개념을 활용해서 아두이노로 시계를 만들어볼 것이다.

# 하드웨어 

- 라즈베리파이4  
- SD card (4GB 이상)
- USB Cam
- 라즈베리파이 전원아답터 (5V 2.5A)
- LED 

**주의: 점퍼선 연결시 케이블을 제거하고 진행합니다.**


## 연결 작업 
### USB camera
USB 카메라를 연결한 후에 아래 명령어로 연결되어 있는 포트 확인  

```bash
lsusb
```

```bash
v4l2-ctl --list-devices
```

### LED 

| [RaspberryPi GPIO](https://docs.arduino.cc/resources/pinouts/A000066-full-pinout.pdf) | LED |
|-----------|------|
|   D19     | SCL  |
|   D18     | SDA  |
|   5V      | VCC  |
|   GND     | GND  |


# 코드 다운로드 

    git clone https://

# 운영체제 

- 64bit Raspbian bookworm (Ver12) 

## 운영체제 확인하는법
터미널에서 아래와 같이 입력한다.
```bash
cat /etc/os-release
```
몇 비트인지 확인하는 법 
```bash
uname -m
```

## 설치  
1. fswebcam 

## USB camera   

```bash 
sudo apt-get install fswebcam
```
## 쵤영하기 
```bash 
fswebcam -d /dev/video0 /[사진경로] 
```



1. open
2. compile

## 업로드  
1. upload

# 동작영상 

Here's a video outlining how it works and a timelapse of it looking after a plant for a week:

[![Mod demo](https://img.youtube.com/vi/E6wkvTG2Ofs/0.jpg)](https://www.youtube.com/watch?v=E6wkvTG2Ofs "Video Title")

# 라이센스 
[GPL 3.0](https://olis.or.kr/license/Detailselect.do?lId=1072&mapCode=010072)
