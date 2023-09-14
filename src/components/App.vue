<template>
  <section class="login">
    <div class="container">
      <div class="login__container">
        <div class="login__fields">
          <div class="login__logo">
            <img src="../assets/login/Logo.svg" alt="" />
          </div>
          <div class="login__fields-container">
            <div class="login__fields-block">
              <h1 class="login__title">Let's get <span>creative!</span></h1>
              <p class="login__subtitle">
                Log in to Artificium to start creating magic.
              </p>
              <login-component></login-component>
            </div>
          </div>
          <div class="login__sign-up">
            <p class="login__sign-up_label">Don’t have an account?</p>
            <a
              href="https://ajax.test-danit.com/front-pages/cards-register.html"
              class="login__sign-up_btn"
              target="_blank"
              >Sign Up</a
            >
          </div>
        </div>
        <div class="login__picture">
          <img src="../assets/login/Illustration.png" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import LoginComponent from "./LoginComponent.vue";
</script>

<style lang="scss" scoped>
@import url("../styles/base.scss");

.container {
  max-width: 1440px;
  margin: 0 auto;
}

.login {
  font-family: Plus Jakarta Sans;
}

.login__container {
  min-height: 100vh;
  display: flex;
}

.login__fields {
  display: flex;
  flex-direction: column;
  flex: 1;
  background-color: #131619;
}
.login__logo {
}
.login__fields-container {
  display: flex;
  flex: 1;
}
.login__title {
  font-size: 36px;
  font-style: normal;
  font-weight: 400;
  line-height: 122%;
  color: #fff;
  margin-bottom: 24px;
}
.login__subtitle {
  font-size: 18px;
  font-style: normal;
  font-weight: 500;
  line-height: 155%;
  letter-spacing: 0.15px;
  color: #9b9c9e;
  margin-bottom: 64px;
}
.login__fields-block {
  margin: auto;
}
.blue {
}

.login__forgot-btn {
}

.login__sign-up {
  display: flex;
  margin: 0px 0px 48px 48px;
}
.login__sign-up_label {
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 150%;
  letter-spacing: 0.15px;
  margin-right: 8px;
  color: #686b6e;
}
.login__sign-up_btn {
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 150%;
  letter-spacing: 0.15px;
  background-image: linear-gradient(45deg, #82dbf7 0%, #b6f09c 100%);
  color: transparent;
  background-clip: text;
}

.login__picture {
  flex: 1;

  img {
    width: 100%;
    height: 100vh;
    object-fit: fill;
  }
}
</style>
