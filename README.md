# 겜플리  
### 이미지・텍스트 기반 나만의 추천 게임플레이리스트  
2021.07.17 [제 12회 투빅스 빅데이터 컨퍼런스](https://user-images.githubusercontent.com/54944069/125618205-bd89b8de-3d78-4c22-b668-5b381af4c7c1.png) 발표작  
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125945988-d7dce43b-fa28-47b3-90c6-ff401520ea74.png" width="720px" alt=""/></a></td>
  </tr>
</table>
  
Steam에서 제공하는 Multimodal 데이터를 다양한 방법으로 이용하여 **개인화된 추천 게임플레이리스트**를 제공하는 서비스입니다.
  
  
## :checkered_flag: Flow Chart   
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125940720-e3d6e88d-6cc0-4d61-9735-51540b6e9e10.png" width="720px" alt=""/></a></td>
  </tr>
</table> 
  
  
#### 1. 게임・유저 데이터  
> NLP method(LDA, Sentiment Analysis)를 통해 Textual Feature를 생성했습니다.  
> 그 외 변수들은 Feature Engineering을 통해 파생변수를 생성했습니다.  
#### 2. Game2Vec  
> Play Sequence, 이미지, 텍스트 데이터를 각각 Prod2Vec, Convolutional AutoEncoder, AutoEncoder를 이용하여  
> Multimodal Feature인 Game2Vec을 생성했습니다.  
#### 3. Recommender System  
> 앞에서 생성한 Game2Vec을 모델 레이어에 추가하여 학습했습니다.  
#### 4. 시연  
> 추천 게임플레이리스트를 제공하는 웹페이지를 구현했습니다.
  
  
## :checkered_flag: Result  
### Model Evaluation  
| Model | Game2Vec 사용 | Test ACC | Test AUC | Test F1 | - |  
| :-: | :-: | :-: | :-: | :-: | :-: |   
| Vanilla GMF | ❌ | 78.51% | 0.7746 | 0.8711 | |  
| GMF | ⭕ | 83.62% | 0.8526 | 0.8956 | |  
| MLP | ⭕ | 81.50% | 0.8391 | 0.8837 | |   
| **NMF** | ⭕ | **84.33%** | 0.8715 | **0.9007** | **:crown: Best Model** |  
| DCN Parallel | ⭕ | 82.31% | 0.8463 | 0.8868 | |  
| DCN Stacked | ⭕ | 82.55% | 0.8500 | 0.8876 | |  
| DeepFM | ⭕ | 80.61% | 0.8194 | 0.8868 | |  
   
* **Multimodal Feature**인 **Game2Vec**을 사용했을 때 모델 성능이 향상했습니다.  
* Neural Collaborative Filtering 계열 모델들의 성능이 좋았습니다.  
  
  
### Web Page  
[:mag: Page Link](https://tobigs-steamgame.github.io/recsys/)  
  
* **서비스 화면**  
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125979454-24dd2fea-aa34-4113-a3cf-ad5c05564ea1.jpeg" width="720px" alt=""/></a></td>
  </tr>
</table>  
  
* **선호 게임 리스트**  
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125979349-516df9c2-ea5b-49ea-9c42-22ca3c538be7.jpeg" width="720px" alt=""/></a></td>
  </tr>
</table>  
  
* **시연 예시1**  
> 선호 반영   
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125979290-85d1f963-7d59-4f07-947c-398f091dc1ba.jpeg" width="720px" alt=""/></a></td>
  </tr>
</table>
  
> 추천
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125979147-66b6fafb-5405-4c80-9f16-6dfd1a9240fd.jpeg" width="720px" alt=""/></a></td>
  </tr>
</table>
  
* **시연 예시2**  
> 선호 반영  
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125978582-14755682-4b09-4821-a659-b200265c8f25.jpeg" width="720px" alt=""/></a></td>
  </tr>
</table>  
   
> 추천   
<table>
  <tr>
    <td align="left"><img src="https://user-images.githubusercontent.com/54944069/125978532-ce682f00-1134-46ba-96b0-119fb71c9df7.jpeg" width="720px" alt=""/></a></td>
  </tr>
</table>  
  
## :checkered_flag: Presentation    
컨퍼런스 발표영상과 보고서입니다. 자세한 분석 내용은 아래 링크를 통해 확인해주세요!  
* [![GoogleDrive Badge](https://img.shields.io/badge/REPORT-405263?style=flat-square&logo=Quip&link=https://drive.google.com/file/d/1VnYsB8k4Fxu6UFhAxuTi4m01BjoH2uwS/view?usp=sharing)](http://www.datamarket.kr/xe/board_pdzw77/74633)
* [![Youtube Badge](https://img.shields.io/badge/Youtube-ff0000?style=flat-square&logo=youtube&link=https://youtu.be/KPS1sD_lcMc)](https://www.youtube.com/watch?v=UpHYyDlUfsQ)
  
  
## :checkered_flag: Contributors ##  
빅데이터 동아리 [ToBig's](http://www.datamarket.kr/xe/) 13기・14기・15기가 함께 하였습니다😃  
 |<img src="https://user-images.githubusercontent.com/54944069/125977338-2c02039f-c78e-4d8e-b29b-d3e190ae7e14.png" width="200" >| <img src="https://user-images.githubusercontent.com/54944069/125926011-173ecd1b-db58-4d69-8aac-e20fbad20b15.jpeg" width="200" height="200" > | <img src="https://user-images.githubusercontent.com/54944069/125942489-e98bbb44-06ab-4675-9540-885635c7999a.JPG" width="200" > |
 | :-: | :-: | :-: | 
 | [Jieun Park](https://github.com/Jieun-Enna) | [Hyerin Lee](https://github.com/hrlee113) | [Donghyun Kim](https://github.com/DataAnalyst486) | 
   
  | <img src="https://user-images.githubusercontent.com/54944069/125942584-5cac01fb-fd28-4e82-88d3-87147edb6908.jpg" width="200" > |<img src="https://user-images.githubusercontent.com/54944069/125942330-26e910a6-82ae-4b68-a4e9-8e5ddf53a534.jpg" width="200" >| <img src="https://user-images.githubusercontent.com/54944069/125941896-ef7e923b-dda5-44a3-b830-9318ad730dff.jpg" width="200" > | 
 | :-: | :-: | :-: |
 | [Seongbeom Lee](https://github.com/SeongBeomLEE) | [Ayeon Jang](https://github.com/JangAyeon) | [Sangyeon Jo]() |  
 
 ## 🏁 File Directory ## 
 
 ```shell
겜플리
|  
├── 1. data
│   ├── steam_game_meta_data_final.csv                # 게임 메타 데이터
│   ├── steam_user_meta_data_final_v1.csv             # 유저 메타 데이터
│   ├── datasteam_reviews_clean_result_train_v2.csv   # 리뷰 데이터
│   ├── norm_game2vec.pickle                          # Game2Vec
│   └── ...
│   
├── 2. prep
│   ├── game_prep.py                # 게임 데이터 preprocessing
│   ├── user_prep.py                # 유저 데이터 preprocessing
│   ├── review_prep.py              # 리뷰 데이터 preprocessing
│   └── dataloader.py               # 게임, 유저, 리뷰 데이터 병합 (final data)
│
├── 3. nlp
│   ├── lda.py                      # LDA
│   └── sentiment.py                # Sentiment Analysis
│
├── 4. embedding # Game2Vec 
│   ├── image_ae.py                 # 게임 이미지 벡터화 (CNN AutoEncoder)
│   ├── text_ae.py                  # 게임 장르 텍스트 벡터화 (AutoEncoder)
│   ├── sequence_prod2vec.py        # 게임 이용 시퀀스 벡터화 (Prod2Vec)
│   └── game2vec.py                 # 최종 Game2Vec 벡터
│
├── 5. model
│   ├── model_prep.py 
│   │ 
│   ├── 4-1. Neural Collaborative Filtering                
│   │   ├── gmf.py                  # Generalized Matrix Factorization
│   │   ├── mlp.py                  # Multi-Layer Perceptron
│   │   └── nmf.py                  # Neural Matrix Factorization
│   │ 
│   └── 4-2. CTR prediction                
│       ├── deepfm.py               # Deep Factorization Machine
│       └── dcn.py                  # Deep Cross Network
│
├── utils.py
└── main.py


```

