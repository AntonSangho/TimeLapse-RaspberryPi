![img](https://pimylifeup.com/wp-content/uploads/2015/02/Raspberry-Pi-Webcam-Server-V1.jpg)

# 타임랩스 만들기  

라즈베리파이와 웹 캠을 활용하여 타임랩스를 만들기


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

# 코드 다운로드 

    git clone https://

# 운영체제 

- 64bit Raspbian bookworm (Ver12) 

## 운영체제 확인하는법
터미널에서 아래와 같이 입력한다.
```bash
```
몇 비트인지 확인하는 법 
```bash
uname -m
```

## 설치  
1. fswebcam 
```bash
sudo apt-get install fswebcam
```

## 촬영하기 
```bash 
fswebcam image.jpg 
```

## 동작스크립트 작성하기
1. webcam 폴더만들기
```bash
sudo mkdir ~/webcam
cd ~/webcam
```

2. bash 스크립트 작성 
```bash
#!/bin/bash

DATE=$(date +"%Y-%m-%d_%H%M")

fswebcam -r 1280x720 --no-banner /home/pi/webcam/$DATE.jpg
```
3. bash 스트립트 권한 설정 
```bash 
chmod +x webcam.sh
```

## 자동으로 촬영하기
1. 스케줄 관리 실행 
```bash
crontab -e 
```
2. 30분 마다 스크립트를 실행하도록 내용 추가
```bash
* * * * * /home/pi/webcam.sh 2>&1
```
소
## 저장된 사진 가져오기 (미확정)   
1. SSH를 통해서 가져오기 
```bash
sudo scp pi@[ip주소]:/home/pi/webcam/[파일명] /[다운로드 받을 경로]
```

## 사진 여러개를 동영상을 만들기
1. 파이썬으로 구현 

# 라이센스 
[GPL 3.0](https://olis.or.kr/license/Detailselect.do?lId=1072&mapCode=010072)

# 참고
[USING A STANDARD USB WEBCAM](https://www-users.york.ac.uk/~mjf5/shed_cam/src/USB%20webcam.html)
