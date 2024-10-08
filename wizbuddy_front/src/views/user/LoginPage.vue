<template>
  <div class="login-page">
    <div class="left-section">
      <img src="@/assets/icons/user/큰 아이콘 부분.png" alt="Wizzbuddy_character" class="character-image" />
    </div>
    <div class="right-section">
      <div class="login-form">
        <form @submit.prevent="onSubmit">
          <div class="input-group">
            <label for="userName">아이디</label>
            <input type="text" id="userName" v-model="userName" placeholder="아이디 입력" />
          </div>
          <div class="input-group">
            <label for="password">비밀번호</label>
            <input type="password" id="password" v-model="password" placeholder="비밀번호 입력" />
          </div>

          <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>

          <div class="login-button">
            <button type="submit" class="login-btn">
              <img src="@/assets/icons/user/로그인.svg" alt="로그인 버튼" />
            </button>
            <button type="button" @click="kakaoLogin" class="kakao-btn">
              <img src="@/assets/icons/user/카카오_로그인.svg" alt="카카오 로그인 버튼" />
            </button>
          </div>

          <div class="login-bottom-btn">
            <button type="button" class="find-id-btn">아이디 찾기</button>
            <p>|</p>
            <button type="button" class="find-password-btn">비밀번호 찾기</button>
            <p>|</p>
            <button type="button" @click="goToSignup" class="signup-btn">회원가입</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';

const userName = ref('');
const password = ref('');
const errorMessage = ref('');
const router = useRouter();

const onSubmit = async () => {
  errorMessage.value = '';

  // 유효성 검증
  if (!userName.value || !password.value) {
    errorMessage.value = '아이디 또는 비밀번호를 입력해주세요.';
    return;
  }

  try {
    const response = await fetch(`http://localhost:8080/users?email=${userName.value}&password=${password.value}`);
    if (!response.ok) throw new Error('서버 응답 오류');

    const data = await response.json();
    if (data.length > 0) {
      const user = data[0];

      // 사용자 정보를 localStorage에 저장
      localStorage.setItem('user', JSON.stringify(user));

      // 사용자 역할에 따라 페이지 이동
      if (user.role === 'admin') {
        router.push('/admin'); // 관리자 페이지
      } else if (user.role === 'employer') {
        router.push('/main?type=employer'); // 사장 페이지
      } else if (user.role === 'employee') {
        router.push('/main?type=employee'); // 직원 페이지
      }
    } else {
      errorMessage.value = '일치하는 회원정보가 없습니다.';
    }
  } catch (error) {
    console.error('로그인 중 오류 발생:', error);
    errorMessage.value = '로그인 처리 중 오류가 발생했습니다.';
  }
};

// 로그인 전 이전 사용자 정보 초기화
onMounted(() => {
  localStorage.removeItem('user');
});

// 카카오 로그인 처리 함수 (구현 예정)
const kakaoLogin = () => {
  console.log('카카오 로그인 시도');
};

// 회원가입 페이지로 이동
const goToSignup = () => {
  router.push('/signup');
};
</script>

<style scoped>

  .login-page {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #F3F7FA;
    gap:200px;    
    height: calc(100vh - 80px);
    width: 100%;
  }
  
  .left-section {
    flex: 0.3;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #F3F7FA;
  }
  
  .character-image {
    width: 100%; 
    max-width: 500px;
    object-fit: contain; 
  }
  
  .right-section {
    flex: 0.3;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #F3F7FA;
  }
  

  .login-form {
    width: 350px; 
    height: 400px;
    text-align: center;
    padding: 20px;
    background-color: white;
    border-radius: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    position: relative; 
  }
  
  .input-group {
    margin-bottom: 15px;
    text-align: left;
  }
  
  input {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border-radius: 4px;
    box-sizing: border-box;
    border: var(--sds-size-stroke-border) solid #D9D9D9;
    background: #F3F7FA;
    box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  }

  .login-button {
    position: absolute;
    bottom: 20px; 
    left: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .login-btn {
  width: 80%;
  padding: 0;
  background-color: transparent;
  border: none;
  cursor: pointer;
  margin-top: 50px;
  margin-bottom: 10px;
  } 
  
  .login-btn img {
    width: 100%;
    height: auto;
    object-fit: contain; /* 이미지가 버튼 안에서 넘치지 않도록 조정 */
  }
  
  .kakao-btn {
  width: 80%;
  padding: 0;
  background-color: transparent; /* 버튼 배경 투명 */
  border: none; /* 테두리 제거 */
  cursor: pointer;
  margin-bottom: 20px;
  }

  .kakao-btn img {
    width: 100%;
    height: 0 auto;
    object-fit: contain; /* 이미지가 버튼 안에서 넘치지 않도록 조정 */
  }

  .login-bottom-btn {
    display: flex;
    justify-content: center;
    gap: 10px;
  }

  .find-id-btn,
  .find-password-btn,
  .signup-btn {
    background-color: white;
    border: none;
    color: #B7B7B8;
    cursor: pointer;
    text-decoration: none; 
  }

  .login-bottom-btn p {
  color: #B7B7B8;
  margin: 0;
  display: flex;
  }

  .error-message {
    font-size: 12px;
    color: red;
  }

</style>
