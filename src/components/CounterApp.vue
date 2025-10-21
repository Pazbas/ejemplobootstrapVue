<template>
  <b-container class="mt-5">
    <b-card>
      <h2 class="text-center">Contador: {{ count }}</h2>

      <b-row class="text-center my-3">
        <b-col>
          <b-button variant="success" @click="increment">+1</b-button>
        </b-col>
        <b-col>
          <b-button variant="danger" @click="decrement">-1</b-button>
        </b-col>
        <b-col>
          <b-button variant="warning" @click="reset">Reiniciar</b-button>
        </b-col>
      </b-row>
    </b-card>

    <b-card class="mt-4">
      <h4>Historial</h4>
      <b-list-group>
        <b-list-group-item
          v-for="(item, index) in history"
          :key="index"
        >
          {{ item }}
        </b-list-group-item>
      </b-list-group>
    </b-card>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      history: []
    };
  },
  methods: {
    increment() {
      this.count++;
      this.history.push(`+1 → ${this.count}`);
    },
    decrement() {
      this.count--;
      this.history.push(`-1 → ${this.count}`);
    },
    reset() {
      this.history.push(`Reinicio desde ${this.count}`);
      this.count = 0;
    }
  }
};
</script>

<style scoped>
.text-center {
  text-align: center;
}
</style>
