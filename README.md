### 4-1 빅데이터분석 기말프로젝트

### 축구팀 우승가능성 분석하기 <br>
: 축구팀의 경기 데이터를 활용하여 해당 팀의 리그 우승 가능성을 분석하고, 성과에 영향을 미치는 주요 요소를 도출
- 데이터셋: premier League(EPL) 경기 기록 데이터<br>
  - shape: 11,113 x 23
  - column: 시즌, 경기날짜, 홈/어웨이 팀/ 홈/어웨이 팀 득점, 결과, 득점 수, 슈팅 수, 유효슈팅 수, 심판, 파울, 경고, 퇴장<br>
  ![image](https://github.com/user-attachments/assets/5f6bd7c9-9d1d-4e51-99f8-e03ce93c423a)

- **데이터 전처리**
  - 필요한 컬럼만 뽑아 시즌 별 승점 순서대로 정리(1995-96 시즌부터는 20개 팀으로 줄였기 때문에 NaN값이 나온다.) <br>
    ![image](https://github.com/user-attachments/assets/b825f8a7-fe25-446b-8e1d-c3c282f53343)<br>

- **분석하기**<br>
  (1) 내가 좋아하는 팀 분석하기
  Wolverhampton Wanderers Football Club
    - 2022년 4월 10일 기준 8위에 위치
    - 득점 기준 내림차순을 했을 때 16위<br>
      => 총 득점이 앞도적으로 높은 리버풀, 맨시티, 아스널과비교하면 골 득점이 순위와 상관관계가 어느 정도 있다는것을 확인 가능<br>
      ![image](https://github.com/user-attachments/assets/825269d1-12b6-4576-bcfe-3424b2c70d42)<br>
      ![image](https://github.com/user-attachments/assets/025dc7e7-f987-4c6f-959a-76f2f11c7184)
 
  (2) 우승팀 분석을 통해 내가 좋아하는 팀 우승 가능성 예측하기
    - min값을 통해 최소 승점이 74점은 되어야 우승할 가능성이 있다는 것을 확인
    - 2022년 4월 10일 기준 49점이며 이후 6경기 남은 상태였다.
    - 전승을 한다고 해도 49+(6*3)=67점이기에 우승은 가능성이 없다.<br>
    ![image](https://github.com/user-attachments/assets/59f51f91-98dd-4d27-84b0-0b111b4b1321)

  (3) 강등팀 분석하기
    - mean과 50%를 봤을 때, 승점이 35점 정도 되면 강등할 가능성이 크다는 것을 알 수 있다.<br>
  ![image](https://github.com/user-attachments/assets/e1388480-ea00-4aec-bfaf-50d4379427e8) ![image](https://github.com/user-attachments/assets/4a5fb4ce-075a-4bac-b68c-33e388fe9fec)

  (4) 공격/수비력 측면에서 본 우승팀들의 공통점 - mean
    - 공격 측면) 경기당 2골, 14번의 슈팅, 6번의 유효슈팅을 하는 것으로 나타났다.
    - 수비 측면) 경기당 실점 0.8골, 파울 10.5번, 퇴장 0.06번이라는 것을 알 수 있다.

  (5) 2022년 울버햄튼과 비교하기 - 우승팀과의 비교를 위해 38경기수로 분석 <br>
      ![image](https://github.com/user-attachments/assets/4f559914-d209-4d66-94fe-f44515a22d52)<br>
      - 공격력은 예상처럼 많이 부족한 결과이다.
      - 수비력은 우승팀과 큰 차이x, but 경고에 대한 수치가 다른 수비력 수치에 비해 0.5인 것으로 보아 수비/경고/퇴장은 큰 차이x
      (+) 1등 멘시티의 공격력과 수비력 비교하기<br>
        ![image](https://github.com/user-attachments/assets/1f2f3a6c-cf02-4838-9b80-6406c187cc11)<br>
        - 공격력에서는 슈팅/유효슈팅, 수비력에서는 실점 부분에서 차이가 크다. 실점을 줄이고 슈팅/유효슈팅 끌어올린다면 상승할 가능성 높다.
      
- 한계
  - 패널티 요소 이외에도 소속 선수의 개인적인 컨디션과 기량에 따라 경기 결과는 매번 달라질 수 있기 때문에 해당 데이터만으로는 정확하게 우승가능성을 분석하는데는 한계가 있을 수 있
다.
  
 
  
