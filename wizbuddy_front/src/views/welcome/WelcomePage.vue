<template>
    <div class="landing-page">
        
      <header class="header">
        <div class="nav-left">
          <img src="@/assets/icons/welcome/logo2.svg" alt="Wiz Buddy Logo" class="logo-img" />
        </div>
        <nav class="nav">
          <ul>
            <li><a href="#">FAQ</a></li>
            <li><a  @click="goToLogin" >로그인</a></li>
          </ul>
        </nav>
      </header>
  
      <section class="hero-section">
        <div class="hero-content">
            <div class="left-logo">
          <img src="@/assets/icons//welcome/leftlogo.svg" alt="Wiz Buddy Logo" class="title" />
          <p class="subtitle">사장님과 아르바이트생을 위한 스마트 매니지먼트 솔루션</p></div>
          <div class="wiz-meaning">
            <p><strong style="font-size: x-large">W(Work)</strong> 업무 효율을 극대화하는 최적의 파트너</p>
            <p><strong style="font-size: x-large">I(Instant)</strong> 즉시 문제를 해결하고 소통을 원활하게</p>
            <p><strong style="font-size: x-large">Z(Zero)</strong> 스트레스 없이 모든 업무를 간편하게 관리</p>
          </div>
        </div>
        <div class="hero-image">
          <img src="@/assets/icons/welcome/blue.svg" alt="Wiz Buddy Character" class="character-img" />
        </div>
      </section>

      <!-- 새로운 섹션 추가 -->
      <section class="extra-section">
    <div class="icon-columns">
        <div class="icon-column">
        <div class="extra-content" >
          <h2>동료들과 즐겁게!</h2>
          <p><strong style="font-weight: bold; font-size: x-large; color: #6F6C6C;">WIZ BUDDY</strong>는 사장님과 직원들을 위한 스마트 관리 솔루션입니다. 업무의 효율성을 높이고 커뮤니케이션을 원활하게 도와주는 다양한 기능을 제공합니다. 
            <br><br>특히 아르바이트생의 스케줄 관리와 출퇴근 기록, 그리고 체크리스트를 통해 실시간으로 업무를 점검할 수 있어, 매장 운영을 더욱 스마트하게 할 수 있습니다.</p>
        </div>
        </div>

        
      <div class="icon-column">
        <div class="icon-box">
        <img src="@/assets/icons/welcome/store.svg" alt="매장 관리" style="width: 130px;
height: 150px;"/>
      </div>
        <div class="icon-box">
          <img src="@/assets/icons/welcome/people.svg" alt="자영업자라면 누구나" />
          <p style="color:#5DA0BD;">자영업자라면 누구나</p>
          <p>자영업을 하는 사장님이라면<br> 누구든 위즈버디와 함께 <br>하실 수 있어요.</p>
        </div>
        <div class="icon-box">
          <img src="@/assets/icons/welcome/Calculator.svg" alt="계산은 이제 그만" />
          <p style="color:#5DA0BD;">계산은 이제 그만</p>
          <p>월급 계산, 보건증 만료일 계산, <br>근로계약서 날짜 계산, 모든 계산 <br>저희가 자동으로 알려드릴게요</p>
        </div>
      </div>

      <div class="icon-column">
        <div class="icon-box">
        <img src="@/assets/icons/welcome/employee.svg" alt="직원 관리"  style="width: 130px;
height: 150px;" />
      </div>
        <div class="icon-box">
          <img src="@/assets/icons/welcome/call.svg" alt="불편함 해소" />
          <p style="color:#E7C61C;">불편함 해소</p>
          <p>쉬는날 원치않는 연락받을 일이 <br>사라져요!</p>
        </div>
        <div class="icon-box" style="padding-top: 20px;">
          <img src="@/assets/icons/welcome/Arrow.svg" alt="대타 걱정 NO"  />
          <p style="color:#E7C61C;">대타 걱정 NO</p>
          <p>‘그날 안되는데 어쩌지...’ <br>항상 하는 고민 <br>글작성과 댓글채택으로 간편하게</p>
        </div>
      </div>
    </div>
  </section>

  <section class="extra2-section">
    <div class="icon-columns2">
      <!-- 첫 번째 컬럼: 왼쪽 이미지 -->
      <div class="icon-column22">
        <img src="@/assets/icons/welcome/mockup1.svg" alt="Wiz Buddy Mockup" class="character-img2" />
      </div>

      <!-- 두 번째 컬럼: 중앙 텍스트 -->
      <div class="icon-column2" >
        <h2>스케줄 관리를 한번에</h2>
        <p>알바생들의 근무 스케줄을 쉽고 간편하게 <br>관리할 수 있도록 도와줍니다. <br>
          근무 시간표를 손쉽게 설정하고 수정할 수 있으며, <br>
          직원들은 근무 일정을 실시간으로 확인할 수 있습니다.</p>
        <ul>
          <li>근무 스케줄 설정 및 변경</li>
          <li>직원별 근무 일정 조회</li>
          <li>공휴일, 변경된 스케줄 실시간 알림</li>
        </ul>
        <button @click="goToLogin">위즈버디 시작하기</button>
      </div>

      <!-- 세 번째 컬럼: 오른쪽 이미지 -->
      <div class="icon-column2">
        <img src="@/assets/icons/welcome/image1.svg" alt="Additional Image" class="character-img3" />
      </div>
    </div>
  </section>


  <section class="extra3-section">
    <div class="icon-columns2">
      <!-- 첫 번째 컬럼: 왼쪽 이미지 -->
      <div class="icon-column2">
        <img src="@/assets/icons/welcome/image2.svg" alt="Additional Image" class="character-img3" />
      </div>

      <!-- 두 번째 컬럼: 중앙 텍스트 -->
      <div class="icon-column2-1">
        <h2 style="text-align: right;"> 업무 체크리스트</h2>
        <p>직원들은 할당된 업무를 실시간으로 확인하고 <br> 완료 여부를 체크할 수 있습니다.   <br> <br>
            관리자는 체크리스트를 통해 <br>업무의 진행 상황을 <br>쉽게 모니터링할 수 있어 <br>업무 관리가 한층 더 편리해집니다.</p>
        <ul>
          <li>실시간 체크리스트 업데이트</li>
          <li> 완료 여부 실시간 확인</li>
          <li>중요한 업무에 대한 알림 기능</li>
        </ul>
        <button style="margin-left: 70px" @click="goToLogin">위즈버디 시작하기</button>
      </div>

      <!-- 세 번째 컬럼: 오른쪽 이미지 -->
      <div class="icon-column22">
        <img src="@/assets/icons/welcome/mockup2.svg" alt="Wiz Buddy Mockup" class="character-img2-1" />
      </div>
    </div>
  </section>

  <section class="extra4-section">
    <div class="icon-columns2">
      <!-- 첫 번째 컬럼: 왼쪽 이미지 -->
      <div class="icon-column22" >
        <img src="@/assets/icons/welcome/mockup3.svg" alt="Wiz Buddy Mockup" class="character-img4"/>
      </div>

      <!-- 두 번째 컬럼: 중앙 텍스트 -->
      <div class="icon-column2" >
        <h2>출퇴근 관리</h2>
        <p>출퇴근 기록을 손쉽게 관리할 수 있는 기능을 제공합니다.  <br>
            직원들은 출근과 퇴근 시 간편하게 기록을 남길 수 있으며,  <br>
            자동으로 근무 시간이 집계되어 관리자는 쉽게 보고서를 <br>작성할 수 있습니다.</p>
        <ul>
          <li>출퇴근 시간 자동 기록</li>
          <li>실시간 근무 시간 집계</li>
          <li>출퇴근 기록 조회 및 수정</li>
        </ul>
        <button @click="goToLogin">위즈버디 시작하기</button>
      </div>

      <!-- 세 번째 컬럼: 오른쪽 이미지 -->
      <div class="icon-column2">
        <img src="@/assets/icons/welcome/image3.svg" alt="Additional Image" class="character-img2" style=" margin-left: 20px;"/>
      </div>
    </div>
  </section>

  <section class="slider-section">
    <h2>다양한 게시판 기능</h2>
    <div class="slider">
      <button @click="prevSlide" class="arrow left-arrow">&lt;</button>
      <div class="slider-track">
        <div
          v-for="(card, index) in cards"
          :key="index"
          class="card"
          :class="{ active: index === activeSlide }"
        >
          <img :src="card.image" alt="" />
        </div>
      </div>
      <button @click="nextSlide" class="arrow right-arrow">&gt;</button>
    </div>
  </section>


  <section class="testimonial-section">
  <div class="testimonial-slider">
    <button @click="prevTestimonialSlide" class="arrow2 left-arrow2">
      <img src="@/assets/icons/welcome/left.svg" alt="leftarrow">
    </button>
    <div class="testimonial-card">
        <div
        v-for="(testimonial, index) in testimonials"
        :key="index"
        class="testimonial"
        :class="{ active: index === activeTestimonialSlide }"
        >
          <img :src="testimonial.img" alt="" />
          <h3>{{ testimonial.name }}</h3>
          <p class="p1" >{{ testimonial.quote }}</p>
          <p class="p2" v-html="testimonial.description.replace(/\n/g, '<br>')"></p>
          
        </div>
    </div>
    <button @click="nextTestimonialSlide" class="arrow2 right-arrow2"><img src="@/assets/icons/welcome/right.svg" alt="rightarrow"></button>
  </div>
</section>
<section class="button-section">
  <button class="cta-button" @click="goToLogin">위즈버디 시작하기</button>
</section>


<section class="start-section">
  <div class="start-content">
    <div class="start-text">
      <h2>한번 시작해보세요!</h2>
      <p>위즈버디의 가치를 느끼실거예요.</p>
    </div>
    <div class="start-images">
      <img src="@/assets/icons/welcome/mockupfinal.svg" alt="Phone Image 1" class="phone-img" />
    </div>
  </div>

  <footer class="footer">
    <div class="footer-content">
      <div class="company-info">
        <img src="@/assets/icons/welcome/logo2.svg" alt="Wiz Buddy Logo" class="footer-logo" />
        <p>회사명: 위즈버디<br>대표자: 아이브<br>사업자 등록번호: 123-456-7890<br>주소: 동작구 보라매로<br>문의: int4byte@gmail.com</p>
      </div>
      <div class="footer-menu">
        <h3>메뉴</h3>
        <ul>
          <li><a href="#">FAQ</a></li>
          <li @click="goToLogin"><a href="#">로그인</a></li>
          <li @click="goToSignup"><a href="#">회원가입</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-copyright">
      <p>© 2024 Int4byte</p>
    </div>
  </footer>
</section>


</div>
</template>

<script>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

import card1 from '@/assets/icons/welcome/card1.svg';
import card2 from '@/assets/icons/welcome/card2.svg';
import card3 from '@/assets/icons/welcome/card3.svg';
import testimonial1 from '@/assets/icons/welcome/label11.svg';
import testimonial2 from '@/assets/icons/welcome/label22.svg';

export default {
  data() {
    return {
      activeSlide: 0,
      activeTestimonialSlide: 0,
      cards: [
        {
          image: card1,
        },
        {
          image: card2,
        },
        {
          image: card3,
        },
      ],
      testimonials: [
        {
          img: testimonial1,
          name: '사장 백경석 & 알바 유제은, 이나현',
          quote: '"매장 관리가 이렇게 쉬워질 줄 몰랐습니다!"',
          description:
            'WIZ BUDDY를 도입한 후 매장 운영이 훨씬 수월해졌습니다. \n 특히, 스케줄 관리와 업무 체크리스트 기능 .... \n 출근과 퇴근 기록도 자동으로 집계되니 일일이 확인할 필요도 없고..',
        },
        {
          img: testimonial2,
          name: '사장 조제훈 & 알바 이서현',
          quote: '"일정 확인과 업무 체크가 쉬워졌어요!"',
          description:
            '무엇보다 근무 스케줄을 실시간으로 확인할 수 있는 게 정말 유용해요.\n 만약 스케줄이 변경되면 알림이 바로 오기 때문에 놓치는 일이 없어요.\n 예전엔 사장님한테 따로 물어봐야 했는데...',
        },
    ],
    };
  },
  methods: {
    nextSlide() {
      this.activeSlide = (this.activeSlide + 1) % this.cards.length;
    },
    prevSlide() {
      this.activeSlide =
        this.activeSlide - 1 < 0
          ? this.cards.length - 1
          : this.activeSlide - 1;
    },
    nextTestimonialSlide() {
      this.activeTestimonialSlide =
        (this.activeTestimonialSlide + 1) % this.testimonials.length;
    },
    prevTestimonialSlide() {
      this.activeTestimonialSlide =
        this.activeTestimonialSlide - 1 < 0
          ? this.testimonials.length - 1
          : this.activeTestimonialSlide - 1;
    },
    goToLogin() {
      this.$router.push('/login');
    },
    goToSignup() {
      this.$router.push('/signup');
    },
  },
};



</script>


<style scoped src="@/assets/css/welcome/welcome.css">

</style>