# 🐶 강아지 목줄 탐지 프로젝트
+ 🏙 __소속__ : 기업데이터를 활용한 AI취업 부트캠프_서울산업진흥원 (2022.10.24 ~ 2023.02.28)  
+ 📅 __프로젝트 기간__ : 2023.02.16 ~ 2023.02.28  
+ 🤓 __팀원__ : 조세은 | 고상현 노지예 이혁수  

## 💡 문제 정의 및 주제 선정  
2021년 대한민국 반려동물 양육인구는 1,500만명을 넘어섰고 그 수 또한 매년 증가하고 있습니다.  
반려견 양육인구 증가하는 속도만큼 매년 사고 또한 함께 끊임없이 발생하고 있습니다.

## 💡 데이터 수집
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

<img width="800" alt="image" src="https://user-images.githubusercontent.com/112691501/221138743-f6764a78-c9d6-4e96-bdbf-23cb3d68542a.png">

