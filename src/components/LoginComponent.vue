<template>
  <form @submit.prevent="login" class="login__form">
    <default-input
      v-model="mail"
      class="login__mail field"
      type="text"
      id="login_mail"
    />
    <default-input
      v-model="password"
      class="login__password field"
      type="text"
      id="login_password"
    />
    <div class="login__remember-container">
      <div class="login__remember-me">
        <input type="checkbox" name="" id="" />
        <p>Remember me</p>
      </div>
      <div class="login__forgot-btn">
        <button>Forgot Password?</button>
      </div>
    </div>
    <div class="login__login-btn">
      <input type="submit" value="Log in" />
    </div>
  </form>
</template>

<script setup>
import { ref } from "vue";
import DefaultInput from "./UI/DefaultInput.vue";

const mail = ref("");
const password = ref("");

async function login() {
  console.log(mail);
  console.log(password);
  try {
    const response = await fetch(
      "https://ajax.test-danit.com/api/v2/cards/login",
      {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({ email: mail.value, password: password.value }),
      }
    );
    if (!response.ok) throw await response.json();

    const token = response.text;
    console.log(token);
    return token;
  } catch (e) {
    return null;
  }
}

name: "login-comoponent";
</script>

<style lang="scss" scoped>
.login__form {
  display: flex;
  flex-direction: column;
}
.login__remember-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 48px;

  button {
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 150%;
    letter-spacing: 0.15px;
    background-image: linear-gradient(45deg, #82dbf7 0%, #b6f09c 100%);
    color: transparent;
    background-clip: text;
  }
}
.login__remember-me {
  display: flex;

  p {
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 150%;
    letter-spacing: 0.15px;
    color: #cdcecf;
  }

  input {
    margin-right: 16px;
  }
}

.login__login-btn {
  input {
    width: 100%;
    padding: 8px 24px;
    border-radius: 12px;
    background: #b6f09c;
    color: var #0c1132;
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 150%;
    letter-spacing: 0.15px;
  }
}
.login__mail {
  margin-bottom: 24px;
}
.login__password {
  margin-bottom: 48px;
}
</style>
