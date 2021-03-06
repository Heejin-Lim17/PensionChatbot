<h1 align="center">
연금 운용에 도움을 주는 챗봇 알림이⚡
</h1>
<p align="center">

</p>
<br>
<div align="center">
    
</div>

<hr>

<h2> 주요 기능과 장점 </h2>
<p>사용자에게 주기적으로 연금 수익률이 높은 상품과 맞춤형 상품을 챗봇 알림으로 알려줍니다.</p><br/>
<p align = "center"></p>
<p>기존에 연금 상품 관련 서비스는 고객이 직접 연금 상품을 찾아보고 여러 조건들을 따진 뒤 골라야 했습니다.<br/>
    하지만 고객 입장에서 수많은 연금 상품 중 무엇이 자신에게 적합한 상품인지 알기는 매우 어렵습니다. 지금 이 순간에도 연금 상품들은 나오고 있기 때문입니다.<br/>
    또한 연금 상품의 수익률은 시간이 지남에 따라 조금씩 달라집니다. 수많은 상품들의 수익률을 지속적으로 파악하는 것은 개인에게 한계가 있습니다.<br/>
    따라서 저희는 고객의 성향을 파악해 그에 맞는 연금 상품을 추천해주어 고객의 선택을 간소화하고, 챗봇을 통해 수익률 알림을 지속적으로 전달해 고객의 묵시적 비용을 감소시켰습니다.<br/>
    또한 알림이 올 때 고객에게 피드백을 받아 고객이 선택한 상품에 만족하는지 파악하여, 다음 상품 추천에 반영합니다.<br/>
</p><br/>


<h2> ChatBot </h2>
<h3> NAVER CLOVA Chatbot </h3>
<p>연금 추천 서비스의 기반으로 저희는 챗봇을 사용했습니다. 네이버의 CLOVA Chatbot을 이용하여 고객이 연금 상품에 대한 다양한 알림을 받을 수 있도록 제작하였습니다.<br/>
    고객이 챗봇을 처음 사용하였을 때, 연금 계좌 연동 페이지를 제공하여 해당 계좌의 핀-어카운트를 서버에 저장합니다.<br/>
    그리고 성향 테스트 설문을 보내주어 고객의 성향을 파악합니다.<br/>
    고객에 성향에 따른 추천 연금 상품들을 챗봇을 통해 제공하고, 고객이 상품을 선택할 수 있습니다.<br/>
    시간이 지난 후, 해당 상품에 대한 수익률 변동 알림 제공과 함께 고객에게 이 상품이 좋은지 나쁜지 피드백을 받아 다음 추천에 반영합니다.
</p>
<p> - NAVER CLOVA Chatbot에 대해 자세히 알고싶으시다면 다음 링크를 참고해주세요. <a href = "https://www.ncloud.com/product/aiService/chatbot"> NAVER CLOVA Chatbot</a></p><br/>


<h2> 사용한 API </h2>
<h3> 농협 API </h3>
<p>고객의 연금저축계좌를 서비스와 연동하기 위해 농협 API를 사용하였습니다.<br/>
    고객에게 생년월일과 계좌번호를 입력받아, /OpenFinAccountDirect.nh를 이용하여 핀-어카운트를 생성하고 데이터베이스에 저장합니다.
</p>
<p> - 농협 API에 대해 자세히 알고싶으시다면 다음 링크를 참고해주세요. <a href = "https://developers.nonghyup.com/service/SE_1010"> 농협 개발자센터 오픈 API 페이지</a></p>

<h3> 금융감독원 오픈 API </h3>
<p>현재 판매되고 있는 다양한 연금상품들의 정보를 얻어오기 위해 금융감독원 오픈 API를 사용하였습니다.<br/>
    http://finlife.fss.or.kr/finlifeapi/annuitySavingProductsSearch.json 을 사용하여 "금융상품명", "금융회사명", "연평균 수익률" 등 다양한 정보를 가져옵니다.<br/>
    가져온 상품 정보들을 데이터베이스에 저장하고, 고객에게 상품 추천을 할 때 꺼내와 사용합니다.
</p>
<p> - 금융감독원 오픈 API에 대해 자세히 알고싶으시다면 다음 링크를 참고해주세요. <a href = "http://finlife.fss.or.kr/PageLink.do?link=openapi/detail04&menuId=2000128"> 금융감독원 오픈 API 페이지</a></p><br/>


<h2> 세부 기능 </h2>
<h3> AWS </h3>
<p>AWS의 EC2를 사용하여 웹 서버를 생성했습니다. 서버를 통해 다수의 사용자가 웹 페이지에 접속할 수 있습니다.<br/>
    EC2를 사용하였기 때문에 트레픽에 따라 서버의 크기가 유동적으로 변경되는 장점이 있습니다.
</p><br/>
    
<h3> Web Pages </h3>
<p>고객의 계좌를 통해 핀-어카운트를 생성하거나 연금 상품들을 보여주기 위해 웹 페이지를 사용합니다.<br/>
    웹 페이지들은 AWS의 EC2 서버에 존재하며 챗봇이 링크를 제공하면 해당 사이트로 접속할 수 있습니다.<br/>
    계좌 연동 페이지로 이동하여 계좌를 연동할 수 있고, 만약 연금저축펀드 계좌가 아직 없다면 계좌 생성 탭을 눌러 계좌 생성이 가능한 어플을 다운받을 수 있습니다.
</p><br/>

<h3> MYSQL </h3>
<p>고객의 핀-어카운트나 금융감독원 api로부터 얻어온 다양한 연금 상품들의 정보를 저장하기 위해 Database로 MYSQL을 사용하였습니다.<br/>
    데이터베이스에 저장된 데이터를 참조하여 다양한 기능을 수행할 수 있습니다.<br/>
    성향 테스트 결과를 고객별로 저장하거나, 연금 상품들의 정보를 가져와 고객별 맞춤 상품을 추천할 때, 혹은 다른 여러 상황에서 사용합니다.
</p><br/>


```xml
NongHyup License
Copyright (c) 2020 PensionChatbot

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
