<template>
<div>
  <form>
       <label>Name:</label>
      <input type="text" required v-model="name">

      <label>Email:</label>
      <input type="email" required v-model="email">

        <label>Category:</label>
      <select v-model="category">
          <option value="oxfords">Oxfords</option>
          <option value="brogues">Brogues</option>
      </select>

  </form>

  <p>Name: {{ name }}</p>
  <p>Email: {{ email }}</p>
  <p>Category : {{ category }}</p>
  </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            email: '',
            category: ''
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
</style>