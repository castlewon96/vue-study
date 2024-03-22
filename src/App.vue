<template>
  <!-- 헤더 -->
  <header class="menu">
    <div class="container">
      <a href="javascript:;" class="logo"><img src="./assets/logo-text.svg" alt="로고" /></a>
      <ul class="menu-list">
        <li v-for="(a, i) in menus" :key="i">
          <a href="javascript:;">{{ a }}</a>
        </li>
      </ul>
      <ul>
        <li><button type="button"><i class="fa-regular fa-lightbulb"></i></button></li>
        <li><button type="button"></button></li>
      </ul>
    </div>
  </header>
  <!-- 헤더 끝 -->

  <!-- 게시글 영역 -->
  <div class="post-area">
    <div class="container">
      <!-- 
        (item, i)중 item은 postTitle 배열의 데이터
        i는 length값 (0 1 2 3 4 5~)
       -->
       <div class="post-area-cont">
        <div class="post-area-item" v-for="(list, i) in list" :key="i">
          <div class="post-area-item__img">
            <img :src="list.image" :alt="list.title" @click="modal = true; listModal = i" />
          </div>
          <a href="javscript:" class="post-area-item__text">
            <h4>{{ list.title }}</h4>
            <p>{{ list.content }}</p>
            <!-- <button v-on:click="">추천</button><span>1</span> -->
          </a>
          <!-- <button @click="recommendAdd" class="btn_recommend">♡</button> -->
          <button id="listFavorite" class="btn_recommend" @click="listFavorite">{{ list.favorite[0] }}</button>
        </div>
       </div>
    </div>
  </div>
  <!-- 게시글 영역 끝 -->

  <div class="list-modal" v-if="modal == true" @click="modal = false">
    <div class="list-modal-item" @click.stop>
      <div class="list-modal-item__img">
        <img :src="list[listModal].image" :alt="list[listModal].title" />
      </div>
      <h4>{{ list[listModal].title }}</h4>
      <p>{{ list[listModal].content }}</p>
      <button type="button" @click="modal = false">닫기</button>
    </div>
  </div>
</template>

<script>

import listData from './assets/js/list.js';

export default {
  name : 'App',
  data() {
    return {
      menus : ['Post', 'Location'],
      list : listData,
      listModal : 0,
      // postTitle : ['첫번째 게시글', '두번째 게시글', '3번째 게시글', '4번째 게시글', '5번째 게시글', '6번째 게시글', '7번째 게시글', '8번째 게시글', '9번째 게시글'],
      // postContent : ['첫번째 글 내용', '두번째 글 내용', '3번째 글 내용', '4번째 글 내용', '5번째 글 내용', '6번째 글 내용', '7번째 글 내용', '8번째 글 내용', '9번째 글 내용'],
      // recommend : [0, 0],
      modal : false,
    }
  },
  // 함수 만드는 공간
  methods : {
    listFavorite() {
      // 클릭 시 list.favorite[0]를 list.favorite[1]로 변경
      this.list.favorite[0] = this.list.favorite[1];
      if(this.list.favorite[0]) {
        this.list.favorite[1];
      }
    }
    // recommendAdd() {
    //   this.list.recommend++;
    // },
  },
  components : {
  }
}
</script>

<style>
@import url('./assets/css/reset.css');
@import url('./assets/css/style.css');
</style>
