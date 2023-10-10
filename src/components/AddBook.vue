<script setup>
import { reactive } from 'vue';

let newBook = reactive({
              title: "",
              cover: "",
              isRead: false,
              isbn: "",
              author: ""
            });

</script>

<template>
        <h1>📖 Adicionar Livro</h1>
        
        <div class="header-btns">
          <button @click="$emit('closeAddBook')" class="btn">
            Fechar x
          </button>
        </div>
     
        <form class="add-form">
           
            <div class="form-control">
            <label>Título</label>
            <input
                v-model="newBook.title"
                type="text"
                name="text"
                placeholder="Adicione o título"
                required
            />
            </div>
            <div class="form-control">
            <label>Capa</label>
            <input
                v-model="newBook.cover"
                type="text" 
                name="cover" 
                placeholder="Adicione o link da imagem de capa"
                required
                />
            </div>
            <div class="form-control">
            <label>Autor</label>
            <input
                v-model="newBook.author"
                type="text"
                name="author"
                placeholder="Adicione o autor"
            />
            </div>
            <div class="form-control">
            <label>ISBN#</label>
            <input 
                v-model="newBook.isbn"
                type="text" 
                name="isbn" 
                placeholder="Adicione o ISBN" 
            />
            </div>
            <div class="form-control form-control-check">
            <input 
                v-model="newBook.isRead"
                type="checkbox" 
                name="readIt" 
                id="readIt" 
                />
            <label for="readIt">Já li o livro</label>
            </div>
     
            <button @click.prevent="$emit('addBook', newBook)" type="submit" class="btn btn-block">Salvar livro</button>
        </form>
</template>