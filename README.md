# BCCD-Detact
혈소판,적혈구,백혈구를 판별

## Location of dataSet
https://public.roboflow.com/object-detection/bccd

### 작업환경
- 장치 이름	DESKTOP-O998J3H
- 프로세서	Intel(R) Core(TM) i7-8700 CPU @ 3.20GHz   3.19 GHz
- 설치된 RAM	16.0GB
- 장치 ID	79976040-AE86-48D2-BE1C-72385C61EAC7
- 제품 ID	00330-80000-00000-AA923
- 시스템 종류	64비트 운영 체제, x64 기반 프로세서
- 펜 및 터치	이 디스플레이에 사용할 수 있는 펜 또는 터치식 입력이 없습니다.

### 모델
YOLOV5

## 순서
  1. 폴더를 만듭니다. : C:\Users\WSU\Desktop\CODE\BCCD
  2. VSCODE를 실행
  3. 터미널을 열고
  4. conda create -n yolov5 python=3.9
  5. VSCODE와 연결 하고
  6. 새 터미널을 엽니다. : (yolov5) C:\Users\WSU\Desktop\CODE\BCCD
  7. git clone으로 yolov5를 내려 받습니다.
  8. move to 'yolov5' Folder
  9. pip install -r requirements.txt
  10. myGlob.py를 만듭니다. 내용은 colab에 있던 2개의 셀을 복사해오고 폴더 위치만 맞춥니다.
```
# 여기서 주의할 것은 데이터 셋의 위치를 잘 맞추기
# 실행하는 폴더에 따라서 상대 경로가 달라지므로
# 절대 경로를 쓰는 것도 괜찮음
from glob import glob
train_img_list = glob('C:/Users/WSU/Desktop/CODE/BCCD/yolov5/dataSet/train/images/*.jpg')
test_img_list = glob('C:/Users/WSU/Desktop/CODE/BCCD/yolov5/dataSet/test/images/*.jpg')
valid_img_list = glob('C:/Users/WSU/Desktop/CODE/BCCD/yolov5/dataSet/valid/images/*.jpg')
print(len(train_img_list), len(test_img_list), len(valid_img_list))

import yaml
if len(train_img_list) > 0 : 
    with open('C:/Users\WSU/Desktop/CODE/BCCD/yolov5/dataSet/train.txt','w') as f:
        f.write('\n'.join(train_img_list) + '\n')
    with open('C:/Users/WSU/Desktop/CODE/BCCD/yolov5/dataSet/test.txt','w') as f:
        f.write('\n'.join(test_img_list) + '\n')
    with open('C:/Users/WSU/Desktop/CODE/BCCD/yolov5/dataSet/val.txt','w') as f:
        f.write('\n'.join(valid_img_list) + '\n')
```
