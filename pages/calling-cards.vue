<template>
  <div class="container">
    <div>
      <h1 class="title">Calling Cards</h1>
      <div class="calling-cards row">
        <template v-for="card in cards">
          <div class="col-sm-6 col-md-4 col-lg-3" v-bind:key="card.image">
            <a v-bind:href="card.link" target="_blank">
              <img v-bind:src="card.image" class="calling-card-banner" />
            </a>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import cards from '~/calling-cards.json'

export default Vue.extend({
  data () {
    return {
      cards
    }
  },

})
</script>

<style>
.calling-card-banner {
  width: 100%;
  padding-bottom: 5px;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
