<script setup>
import { useRouter, useRoute } from 'vue-router';
const router = useRouter()
const route = useRoute()

import { ref } from 'vue'
import { bookstore } from '../assets/js/bookstore'
const books = ref(bookstore)

import CardBooks from '../views/CardBooks.vue'


const openBook = (bId) => {
  const routeParams = {
    name: 'BookPreview',
    params: {
      bookId: bId
    }
  }
  router.push(routeParams)
}

// const nbPerPage = 8
// const nbPages = Math.ceil(books.value.length / nbPerPage)

// const paginationHandler = (page) => {
//   console.log('go to page', page)
//   router.push({
//     query: { page: page }
//   })
//   const start = (page - 1) * BOOKS_PER_PAGE
//   const end = page * BOOKS_PER_PAGE
//   localBookstore.value = bookstore.slice(start, end)
// }

// paginationHandler(route.query.page)

// console.warn({ nbPages })
</script>

<template>
  <main>

    <div class="tm-main-content container">
      <section class="tm-margin-b-l">
        <header>
          <h2 class="tm-main-title">Welcome to our bookstore</h2>
        </header>

        <p>Shelf HTML template is provided by Tooplate. Please tell your friends about it. Thank you. Images are from
          Unsplash website. In tincidunt metus sed justo tincidunt sollicitudin. Curabitur magna tellus, condimentum
          vitae consectetur id, elementum sit amet erat.</p>

        <div class="tm-gallery">
          <div class="row">
            <CardBooks style="cursor: pointer;" v-for="book in books" :id=book.id :title=book.title :author=book.author
              :cover=book.cover @click="openBook(book.id)" />

          </div>
        </div>
        <nav class="tm-gallery-nav">
          <ul class="nav justify-content-center">
            <li v-for="pageNumber in nbPages" :key="pageNumber" class="nav-item" @click="paginationHandler(pageNumber)">
              <a class="nav-link" href="">{{ pageNumber }}</a>
            </li>
          </ul>
        </nav>
      </section>

    </div>


  </main>
</template>
