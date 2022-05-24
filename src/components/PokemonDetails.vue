<template>
  <div class="detail font-mono text-lg">
    <div class="detail-view" v-if="show">
      <div v-if="pokemon" class="image">
        <img :src="imageUrl + pokemon.id + '.png'" alt="" />
      </div>
      <div v-if="pokemon" class="data">
        <h2>{{ pokemon.name }}</h2>
        <div class="property">
          <div class="left">Base Experience</div>
          <div class="right">{{ pokemon.base_experience }} XP</div>
        </div>
        <div class="property">
          <div class="left">Height</div>
          <div class="right">{{ pokemon.height / 10 }} m</div>
        </div>
        <div class="property">
          <div class="left">Weight</div>
          <div class="right">{{ pokemon.weight / 10 }} kg</div>
        </div>
        <h3>Pokemon Types</h3>
        <div class="types">
          <div
            class="type"
            v-for="(value, index) in pokemon.types"
            :key="'value' + index"
          >
            {{ value.type.name }}
          </div>
        </div>
        <h3>Abilities</h3>
        <div class="abilities">
          <div
            class="ability"
            v-for="(value, index) in pokemon.abilities"
            :key="'value' + index"
          >
            {{ value.ability.name }}
          </div>
        </div>
      </div>

      <h4 class="button" v-else>Sorry, pokemon was not found</h4>
      <button class="close font-mono text-sm" @click="closeDetail">
        close
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["pokemonUrl", "imageUrl"],
  data: () => {
    return {
      show: false,
      pokemon: {},
    };
  },
  methods: {
    fetchData() {
      let req = new Request(this.pokemonUrl);
      fetch(req)
        .then((resp) => {
          if (resp.status === 200) return resp.json();
        })
        .then((data) => {
          this.pokemon = data;
          this.show = true;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    closeDetail() {
      this.$emit("closeDetail");
    },
  },
  created() {
    this.fetchData();
  },
};
</script>

<style>
.detail {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  position: fixed;
  top: 0;
  left: 0;
  padding: 90px 10px 10px;
  width: calc(100% - 20px);
  height: calc(100vh - 20px);
  align-items: center;
  color: #110101;
}

.detail-view {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: relative;
  padding: 36px 10px 0px;
  background-color: rgb(220, 221, 228);
  border-radius: 25px;
}

.image {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: -75px;
  width: 120px;
  height: 120px;
  background-color: rgba(241, 237, 15, 0.418);
  border-radius: 50%;
  border-color: rgba(255, 255, 255, 0.233);
  overflow: hidden;
}

.button {
  background-color: #0e0f0f;
  padding: 10px 10px 10px;
  height: 40px;
}

h4 {
  text-transform: capitalize;
  color: rgb(250, 235, 235);
  padding: 10px 10px;
  border-radius: 50px;
  padding: 5px 10px;
  border-radius: 10px;
  font-size: 12px;
  letter-spacing: 10px;
  text-transform: capitalize;
  word-wrap: none;
  word-break: keep-all;
  align-items: center;
}

h2 {
  text-transform: capitalize;
  color: rgb(243, 237, 237);
  background-color: #101110;
  padding: 10px 20px;
  border-radius: 50px;
  padding: 5px 10px;
  border-radius: 10px;
  font-size: 12px;
  letter-spacing: 10px;
  text-transform: capitalize;
  word-wrap: none;
  word-break: keep-all;
  align-items: center;
}

.data {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  width: 100%;
  margin-bottom: 40px;
  color: #110101;
}

.property {
  width: 90%;
  max-width: 400px;
  border-bottom: 1px solid rgb(10, 7, 7);
  margin-bottom: 10px;
  float: left;
  float: right;
}

h3 {
  width: 90%;
  max-width: 400px;
  border-bottom: 1px solid rgb(14, 11, 11);
  color: #110101;
}

.types,
.abilities {
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  width: 90%;
  max-width: 400px;
  justify-content: center;
  color: #110101;
}

.type,
.ability {
  margin: 1px 1px 0px 0px;
  padding: 1px 8px;
  border-radius: 10px;
  color: rgb(250, 245, 245);
  font-size: 13px;
  letter-spacing: 2px;
  text-transform: capitalize;
  word-wrap: none;
  word-break: keep-all;
  align-items: center;
}

.type {
  background-color: #0a0a0a;
}
.ability {
  background-color: #0c0c0c;
}

.close {
  outline: none;
  border: none;
  border-radius: 5px;
  background-color: rgb(252, 241, 241);
  color: rgb(8, 8, 8);
  padding: 1px 5px;
  margin-top: 10px;
  margin-bottom: 10px;
  font-size: 14px;
  cursor: pointer;
}


</style>
