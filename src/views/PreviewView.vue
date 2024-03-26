<script setup>
import { ref } from 'vue'
import { useRoute } from 'vue-router'

import { bookstore } from '@/assets/js/bookstore';
const books = ref(bookstore)

const route = useRoute()

const bookId = route.params.bookId


// console.log(books,route.params.bookId)

const foundBook = ref(null)

const matchId = () => {
    for (let book of books.value) {
        if (book.id === bookId) {
            foundBook.value = book
            break;
        }
    }
    console.log(foundBook)
}

matchId()


</script>

<template>
    <div class="container">

        <div class="tm-main-content no-pad-b">

            <section class="row tm-item-preview">
                <div class="col-md-6 col-sm-12 mb-md-0 mb-5">
                    <img :src="'/src/assets/img/' + foundBook.cover" alt="Image" class="img-fluid tm-img-center-sm">
                </div>
                <div class="col-md-6 col-sm-12">
                    <h2 class="tm-blue-text tm-margin-b-p">{{ foundBook.title }}</h2>
                    <p class="tm-margin-b-p">{{ foundBook.author }}</p>

                </div>
            </section>

            <div class="tm-gallery no-pad-b">
                <!-- spacer -->
            </div>

        </div>


    </div>
</template>

<style scoped></style>