<template>
  <div class="menu">
    <div class="container">
      <a href="javascript:;"><img src="./assets/logo.png" alt="로고" /></a>
      <a href="javascript:;" v-for="(a, i) in menus" :key="i">{{ a }}</a>
    </div>
  </div>
  <div class="post-area">
    <div class="container">
      <div class="post-area-item" v-for="(a, i) in postTitle" :key="i">
        <a href="javscript:">
          <h4>{{ postTitle[i] }}</h4>
          <p>{{ postContent[i] }}</p>
        </a>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name : 'App',
  data() {
    return {
      menus : ['Post', 'Location'],
      postTitle : ['첫번째 게시글', '두번째 게시글'],
      postContent : ['첫번째 글 내용', '두번째 글 내용']
    }
  },
  components : {
  }
}
</script>

<style>
@font-face {
  font-family: 'Pretendard-Regular';
  src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Regular.woff') format('woff');
  font-weight: 400;
  font-style: normal;
}
html {
  font-size: 16px;
  font-family: 'Pretendard-Regular';
  line-height: 1.1;
  color: #333;
  box-sizing: border-box;
}
.container {
  max-width: 1240px;
  width: 100%;
  padding: 0 15px;
  margin: 0 auto;
}
.title {
  font-size: 22px;
  font-weight: bold;
  margin-bottom: 20px;
}
.menu {
  padding: 10px 0;
  background: #000;
}
.menu .container {
  display: flex;
  align-items: center;
}
.menu img {
  width: 30px;
}
.menu a {
  padding: 0 15px;
  color: #fff;
}
.post-area {
  padding-top: 60px;
  text-align: center;
}
.post-area .post-area-item {
  border: 1px solid #000;
  border-left: none;
  border-right: none;
}
.post-area .post-area-item + .post-area-item {
  border-top: none;
}
.post-area .post-area-item a {
  display: block;
  padding: 30px 0;
}
.post-area h4 {
  font-size: 18px;
  font-weight: bold;
}
@import url('./assets/reset.css');
</style>
