<template>
  <div class="searchbar">
    <form @submit.prevent="setPokemonUrl">
      <input
        type="text"
        placeholder="Type pokemon's name"
        v-model="searchvalue"
      />
    </form>
   
  </div>
</template>

<script>
export default {
  props: ["apiUrl"],
  data: () => {
    return {
      searchvalue: "",
    };
  },
  methods: {
    setPokemonUrl(url) {
    
     this.searchvalue = this.searchvalue.toLocaleLowerCase(); // toLowerCase
      if (this.searchvalue !== "")
        this.$emit("setPokemonUrl", this.apiUrl + this.searchvalue);
    },
  },
};
</script>

<style scoped>
.searchbar {
  position: relative;
  width: 100%;
  max-width: 510px;
  padding-bottom: 20px;
}

input {
  border: none;
  outline: none;
  border-radius: 5px;
  padding: 10px 40px 10px 10px;
  width: calc(100% - 50px);
  font-size: 1rem;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2), 0 10px 10px rgba(0, 0, 0, 0.2);
  color: #121213;
  margin-top: 10px;
  margin-bottom: 10px;
}
</style>
