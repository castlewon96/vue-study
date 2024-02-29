<template>
  <div class="menu">
    <div class="container">
      <a href="javascript:;" class="logo"><img src="./assets/logo-text.svg" alt="로고" /></a>
      <ul class="menu-list">
        <li v-for="(a, i) in menus" :key="i">
          <a href="javascript:;">{{ a }}</a>
        </li>
      </ul>
    </div>
  </div>
  <div class="post-area">
    <div class="container">
      <!-- 
        (item, i)중 item은 postTitle 배열의 데이터
        i는 length값 (0 1 2 3 4 5~)
       -->
      <div class="post-area-item" v-for="(item, i) in postTitle" :key="i">
        <a href="javscript:">
          <h4>{{ item }}</h4>
          <p>{{ postContent[i] }}</p>
          <!-- <button v-on:click="">추천</button><span>1</span> -->
        </a>
        <button @click="recommendAdd" class="btn_recommend">추천<span>{{ recommend[i] }}</span></button>
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
      postContent : ['첫번째 글 내용', '두번째 글 내용'],
      recommend : [0, 0],
    }
  },
  // 함수 만드는 공간
  methods : {
    recommendAdd() {
      this.recommen++;
    },
  },
  components : {
  }
}
</script>

<style>
@import url('./assets/css/reset.css');
@import url('./assets/css/style.css');
</style>
