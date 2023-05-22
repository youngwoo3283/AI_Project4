# AI_Project4


# 주의사항
원래는 train_docs.json과 문장생성피클링된 모델을 올리려했으나 대용량이여서 안올려져서 이거는 따로 올린 AI_15_최영우.ZIP에 있습니다

---
# 파일 소개
train_docs와 test_docs.json  : 얘네는 토큰화된 파일이어서 얘네를 코랩에 세션장소에 먼저 업로드를 하시면 다시 토큰화를 할 필요없이  코드 진행이 빨리 됩니다

감성분석.pkl과 문장생성.pkl : 감성분석 및 문장생성 모델을 피클링한것으로 이거를 세션장소에 업로드하시면 fit과 같은 과정이 필요없습니다

naver_shopping : 네어버 쇼핑 

---

# 리뷰 생성기 프로젝트

자연어 처리를 이용해서 키워드를 입력하면 해당 키워드를 가지고 관련 리뷰를 만들어 주도록 함. 데이터는 네이버 쇼핑 리뷰 데이터를 사용함. 모델은 lstm의 구조를 사용한 커스텀 모델을 사용하였음. 


# 문제 상황

배달앱이나 쇼핑몰등 최근 리뷰는 어디에든 존재한다. 표현력이 부족한 고객 입장에서는 부정적이든 긍정적이든 어떻게 리뷰를 작성할 지 애매 할때가 있고 업주의 입장에서는 리뷰를 한명 한명 일일히 작성하기 어려울 때가 종종 있어서, 리뷰 생성기를 통해서 업주는 시간을 절약하고, 고객은 리뷰를 작성하는데에 도움을 줄 수 있도록 함

# 프로젝트 진행 과정

데이터를 가져와서, 토큰화를 진행한후에 lstm모델에 넣어서 학습시켜서 모델링을 한후에 키워드를 넣으면 해당 키워드에 맞는 문장을 생성 하도록 함. 문장이 생성되면 해당 문장을 감성분석하여서 해당 문장이 옳게 만들어졌는지 검증하고 제대로 됬다면 출력하고 감성분석이 틀리다면 다시 문장을 생성하도록 함


![image](https://github.com/youngwoo3283/AI_Project4/assets/69841073/2979116a-d676-4714-aa90-af1651b6332d)


![image](https://github.com/youngwoo3283/AI_Project4/assets/69841073/729acc13-fd90-4906-8fd0-5fa8c163f1ae)





# 프로젝트 결과

모델 성능의 경우 0.8이상정도가 나와서 기준모델보다 높게 나온 것을 확인 할  수 있고 LSTM의 경우에도 0.9 이상이 나와서 높게 나온것을 확인 할 수 있었고, 예를 들어 '좋아요'라는 키워드를 넣으면 '튼튼하고 좋아요' 라는 문장등을 생성하였고 감성분석에도 긍정적이라는 결과를 얻을 수 있었음


# 느낀점 및 자체 평가

1. 데이터가 적다보니 모르는 단어가 나왔을경우에는 임의로 단어가 나오게 된다.
- 사용자가 감성리뷰시에 부정으로 예측될것 같은 단어를 넣을때 혹은 긍정으로 예측할 것 같은 단어를 사용시에만 효과가 있다.
- 인터넷 용어나 은어는 반응을 할 수 없다. 이경우에는 더 많은 데이터가 필요하다고 느꼇다.
- 나중에 기회가 된다면 크롤링이나 대규모 데이터를 구축해서 더 좋은 프로그램을 만들고 싶다.


2. 리뷰생성후에 감성리뷰를 거치는 파이프라인을 구축하려고하였는데 문장을 다시 생성하는 과정에서 문제가 발생하여서 발표에는 소개하지 못하였습니다

3. 이게 감성분석이나 리뷰생성 할 때 하나를 할 때에도 시간이 몇 초 가량 걸려서 대규모 시행은 시간이 걸려서 비효율적인 것 같다.
>> 시간을 줄이기 위한 해결책을 찾아봐야 겠다.

4. 다른 모델을 사용해서 하려고 하는데 import 오류로 계속해서 실패를 하여서 못한게 하나가 있었고 하나는 이미 서비스 종료를 해서 다양한 모델을 시험할 수 없었던게 아쉬웠다.


