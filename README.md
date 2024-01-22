# VEEM VR 데이터를 이용한 예측 및 분류 모델 개발
![image](https://github.com/DayenaJeong/DLTeam2/assets/114856982/96b09620-dddf-4642-b443-fe7aa78de11e)

## 1. 데이터 변수 특성 결정
### 1) 시선 움직임
- 단계 별 소요 시간
- 이상치 개수 및 비율
- 목표 패널 기준 좌표 산만도
### 2) 몸 움직임
- 테스트 동안 움직인 총 거리
- 평균 움직임 속도 구하기
### 3) 공통 변수 설정
- error 총 횟수
- 뒤로가기 없이 한 번에 맞은 횟수
- 테스트 수행하는 데 걸린 시간
- 비밀번호 틀린 횟수
## DL_team2_code 실행 파일 경로 변경 설명
코드 실행 전에 꼭 아래 코드의 파일 경로 설정을 완료해 주시고 실행해 주세요.

1. path 는 eyerpt, rpt 데이터가 들어가 있는 폴더 경로에 해당합니다. 

2. SNSB_path 는 SNSB 점수 데이터 csv 파일 경로에 해당합니다.

3. data_save_path 는 eyerpt feature csv 파일 저장 경로입니다. 경로 지정 시에 파일 이름을 panel_time.csv 파일로 설정해주세요.

4. path2 는 VEEM 대상자 정보.csv 파일 경로에 해당합니다. 

5. modify_path 는 rpt feature csv 파일 저장 경로입니다. 경로 지정 시에 파일 이름을 result_modify.csv 파일로 설정해주세요.

6. final_path 는 최종 전처리 결과 파일 (eyerpt feature csv + rpt feature csv)경로에 해당합니다. 경로 지정 시에 파일 이름을 final_result.csv 파일로 설정해주세요.

7. "이 다음부터는 rpt data 변수 전처리 과정입니다." 부분의 하위 코드 중 "3. csv파일을 Dataframe으로 읽어 각각 변수에 지정해준다."  코멘트 바로 아래 for문의 코드의 경로를 
    'path경로/rpt_data/' 설정해주세요.  예시 -> /content/딥러닝 텀 프로젝트 배포 VEEM 데이터/VEEM VR 데이터/rpt_data/
                                               (                                       path 경로 부분                                            )(       )

 rpt data 전처리 과정에서 eyerpt와 rpt 파일을 분리 해서 전처리를 진행하기 위해서 파일의 이름이 바뀌므로 파일 경로 설정이 잘못되었을 경우 재실행시 계속해서 오류가 발생할 수 있습니다. 
 패스 경로 설정 누락으로 인한 코드 실행 오류시에는 데이터 파일 폴더를 지우고 데이터 파일을 리셋하여야 합니다. 

## SNSB score Regression model 설명
SNSB score는 같은 모델로 테스트 별로 각각 학습이 진행되었습니다. 

 모델 결과 실행 시 test_num 바꿔가면서 설정해주세요! 예시 -> test_num = 1
 1 : DST_F+B
 2 : S-K-BNT
 3 : RCFT_copyscore
 4 : SVLT_delatedrecall
 5 : K-TMT-E_B
 
 테스트 별 모델 저장은 path경로에 저장됩니다. 
 모델 파일 이름은 regression_(test 번호).h5 로 저장됩니다. 
