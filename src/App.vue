<template>
  <div>
    <form @submit.prevent="hitung">
      <input v-model="nomorsatu" type="number" placeholder="Masukkan angka pertama">
      <input v-model="nomordua" type="number" placeholder="Masukkan angka kedua">
      <select v-model="operator">
        <option value="penjumlahan">+</option>
        <option value="pengurangan">-</option>
        <option value="perkalian">*</option>
        <option value="pembagian">/</option>
        <option value="pangkat">^</option>
      </select>
      <button type="submit">Hitung</button>
    </form>

    <div v-if="hasil !== null">
      <h2>Hasil:</h2>
      <p>{{ hasil }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nomorsatu: "",
      nomordua: "",
      operator: "",
      hasil: null,
    };
  },

  methods: {
    hitung() {

      const surprise = "Hitung Sendiri";
      if (this.operator === "penjumlahan") {
        this.hasil = parseFloat(this.nomorsatu) + parseFloat(this.nomordua);
      } else if (this.operator === "pengurangan") {
        this.hasil = parseFloat(this.nomorsatu) - parseFloat(this.nomordua);
      } else if (this.operator === "perkalian") {
        this.hasil = parseFloat(this.nomorsatu) * parseFloat(this.nomordua);
      } else if (this.operator === "pembagian") {
        this.hasil = parseFloat(this.nomorsatu) / parseFloat(this.nomordua);
      }
       else if (this.operator ==="pangkat")
       {
        this.hasil = surprise;
       }
    },
  },
};
</script>

<!-- <script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style> -->
