<script setup>
import { useBookStore } from "./stores/book.js";
import { RouterLink, RouterView } from 'vue-router'

// storeからのデータ
const booksStore = useBookStore()
const books = booksStore.books

</script>


<template>
  <header>
    <div class="header-left">
    </div>
    <div class="header-right">
      <h1>ReadingApp</h1>
    </div>
  </header>

  <main >
    <div class="main-left">
      <div class="books" v-for="book in books" :key = "book.id">
        <h2>{{ book.title }}</h2>
        <p>{{ book.summary }}</p>
        <p>{{ book.learning }}</p>
        <p>{{ book.star }}</p>
        <p>{{ book.date }}</p>
      </div>
    </div>

    <div class="main-right">
    </div>
  </main>

  <footer>
  </footer>
</template>


<style>

/* 　　　ページ構成デザイン　　　 */
header {
  position: fixed;
  margin-top: 0px;
  padding-top: 5px;
  padding-bottom: 5px;
  width: 1200px;
  background-color: #f7f7f7;
  display:flex
}

.header-left{
  width: 10%;
  margin-right: 3%;
}

.header-right{
  width: 87%;
  margin-top: 3%;
}

main{
  padding-top: 180px;
  padding-bottom: 150px;
  width: 1200px;
  background-color: #fff;
  display:flex
}

.main-left{
  width: 70%;
  margin-right: 5%;
  background-color: #f7f7f7;
  padding: 5%;
}

.main-right{
  width: 25%;
  background-color: #f7f7f7;
  padding: 5%;
}

footer{
  position: fixed;
  bottom: 0;
}
/* 　　　ページ構成デザイン　　　 */


/*      booksデザイン　　　　　 */
.books {
  background-color: #fff;
  padding: 20px;
  margin-bottom: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.books p{
    padding-top: 2%;
}

.books h2 {
  color: #333;
  border-left: solid 3px rgb(0, 189, 126);/*左線*/
  margin-bottom: 5px;
}
/*      booksデザイン　　　　　 */

</style>
