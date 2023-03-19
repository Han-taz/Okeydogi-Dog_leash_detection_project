# 🐶 강아지 목줄 탐지 프로젝트
+ 🏙 __소속__ : 기업데이터를 활용한 AI취업 부트캠프_서울산업진흥원 (2022.10.24 ~ 2023.02.28)  
+ 📅 __프로젝트 기간__ : 2023.02.16 ~ 2023.02.28  
+ 🤓 __팀원__ : 조세은 | 고상현 노지예 이혁수  
    
  <img width="800" alt="image" src="https://user-images.githubusercontent.com/112691501/221145815-04af1380-4db0-4276-b9e9-7e069561d905.png">
# 나의 역할 
## 저는 데이터를 수집하고 yolo 모델을 사용하여 cctv영상 속 반려견을 찾는 역할을 맡았습니다. 처음 수집한 데이터로 전이학습한 yolov5는 map가 0.64정도에 프레임에 반려견이 있어도 찾아내지 못하기도 했습니다. 그래서 이 문제를 해결하기 위해 기존 데이터셋을 엎고 새로운 데이터를 추가 수집하고 yolov7모델을 사용하는 등 시행착오를 거쳐 map 0.83까지 올리고 거의 모든 프레임에서 반려견을 탐지하는 모델을 만들었습니다.
## 💡 문제 정의 및 주제 선정  
매년마다 반복되는 목줄 미착용으로 인한 개물림 사고는 견주의 '우리집 개는 안물어요'와 같은 안일한 인식에서 비롯됩니다. 정부는 개물림 사고 예방에 힘쓰고 있으나 단속 인력부족 등의 이유로 정책의 효과는 미비합니다. OKEYDOGI 팀은 AI 기술로 목줄 착용 여부를 탐지할 수 있다면 인력부족 문제를 해결할 수 있다는 기대로 서비스를 구상하였습니다.  

## 💡 데이터 수집  
반려견 목줄 탐지 모델을 학습시키기 위해 사용된 데이터셋은 다음과 같습니다.  
+ __Kaggle__   
[Stanford Dogs Dataset](https://www.kaggle.com/datasets/jessicali9530/stanford-dogs-dataset), [Cats-vs-Dogs](https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset), [Cat and Dog](https://www.kaggle.com/datasets/tongpython/cat-and-dog)  
+ __Roboflow__   
[Dog with Leash](https://universe.roboflow.com/animal-detection/dog-with-leash/dataset/4), [Microsoft COCO 2017 Dataset](https://public.roboflow.com/object-detection/microsoft-coco-subset)
+ __Public Data__   
keyword : walk with dog, 반려견 산책
+ __Youtube__   
keyword : dog bite attack, cctv live cam

## 💡 모델링  
### ✅ Process  
<img width="800" alt="image" src="https://user-images.githubusercontent.com/112691501/221136952-7498e6b1-f259-4408-a4b2-4e440a200622.png">    
  
1️⃣ 영상 Input    
2️⃣ __Yolo__ (Object detection) : 반려견 위치 찾기  
3️⃣ Crop : Yolo의 bounding box + 상하좌우 20px 크롭  
4️⃣ __ResNet__ (Binary Classification) : 목줄 착용 여부 분류  
5️⃣ 안내멘트 출력  
  
## 💡 서비스 구현  
공원, 백화점 등 시설 관리자는 관리자 웹페이지를 통해 다음과 같은 정보를 얻을 수 있습니다.  
✅ 오늘의 __목줄 미착용 알림 횟수__  
✅ 전일 시간대별 알림 횟수  
✅ 오늘 시간대별 알림 횟수  
✅ 오늘의 알림 기록   
  
<img width="800" alt="image" src="https://user-images.githubusercontent.com/112691501/221138743-f6764a78-c9d6-4e96-bdbf-23cb3d68542a.png">

