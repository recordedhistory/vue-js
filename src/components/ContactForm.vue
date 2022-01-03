<template>
<div>
  <form @submit.prevent="handleSubmit"  @submit="toggleModal">
       <label>Name:</label>
      <input type="text" required v-model="name">

      <label>Email:</label>
      <input type="email" required v-model="email">

        <label>Category:</label>
      <select required v-model="category">
          <option value="oxfords">Oxfords</option>
          <option value="brogues">Brogues</option>
      </select>

       <label>Message:</label>
      <input type="textarea" required v-model="textarea">

        <div class="submit">
        <button>Submit</button>
    </div>
  </form>
     <div v-if="showModal">
    <Modal :name="name" :email="email" :category="category" :textarea="textarea" @close="toggleModal" />
    </div>


  <!-- <p>Name: {{ name }}</p>
  <p>Email: {{ email }}</p>
  <p>Category: {{ category }}</p>
  <p>Message: {{ textarea }}</p> -->
  </div>
</template>

<script>
import Modal from './Modal.vue'
export default {
    components: { Modal },
    data() {
        return {
            name: '',
            email: '',
            category: '',
            textarea: '',
            showModal: false
        }
    },
    methods:{
        toggleModal() {
            this.showModal = !this.showModal
        },
        handleSubmit() {
            console.log('form submitted')
        }
    }
}
</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}
label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input, select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}
.prev, .next, .submit button {
    background: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
}
.submit {
    text-align: center;
}
</style>