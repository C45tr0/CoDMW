<template>
  <div class="container">
    <div>
      <h1 class="title">Calling Cards</h1>
      <b-form-checkbox-group
        id="rarity-checkbox-group"
        v-model="rarities"
        name="rarity-checkbox-group"
      >
        <b-form-checkbox value="Base" class="rarity base">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
          </svg>
          Base
        </b-form-checkbox>
        <b-form-checkbox value="Common" class="rarity common">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
            <path d="M8.04 12l4.03-4.03L16.102 12l-4.03 4.03z"></path>
          </svg>
          Common
        </b-form-checkbox>
        <b-form-checkbox value="Rare" class="rarity rare">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
            <path d="M12.842 12.005l4.03-4.03 4.031 4.03-4.03 4.03zM3.238 11.995l4.03-4.03 4.031 4.03-4.03 4.03z"></path>
          </svg>
          Rare
        </b-form-checkbox>
        <b-form-checkbox value="Epic" class="rarity epic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
            <path d="M12.842 12.005l4.03-4.03 4.031 4.03-4.03 4.03zM8.035 16.802l4.03-4.03 4.031 4.03-4.03 4.03zM3.238 11.995l4.03-4.03 4.031 4.03-4.03 4.03z"></path>
          </svg>
          Epic
        </b-form-checkbox>
        <b-form-checkbox value="Legendary" class="rarity legendary">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
            <path d="M12.842 12.005l4.03-4.03 4.031 4.03-4.03 4.03zM8.045 7.198l4.03-4.03 4.03 4.03-4.03 4.03zM8.035 16.802l4.03-4.03 4.031 4.03-4.03 4.03zM3.238 11.995l4.03-4.03 4.031 4.03-4.03 4.03z"></path>
          </svg>
          Legendary
        </b-form-checkbox>
      </b-form-checkbox-group>
      <div class="calling-cards row">
        <template v-for="card in cards">
          <div class="col-sm-6 col-md-4 col-lg-3 calling-card-container" v-bind:key="card.id">
            <a v-bind:href="card.link" target="_blank">
              <img v-if="card.image" v-bind:src="card.image" class="calling-card-banner" />
              <video v-if="card.video" autoplay="autoplay" muted="muted" playsinline loop="loop" class="calling-card-banner">
                <source v-bind:src="card.video" v-bind:type="card.type" />
              </video>
            </a>
            <span>
              <span v-bind:class="'rarity ' + card.rarity.toLowerCase()">
                <template v-if="card.rarity == 'Base'">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
                  </svg>
                </template>
                <template v-if="card.rarity == 'Common'">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
                    <path d="M8.04 12l4.03-4.03L16.102 12l-4.03 4.03z"></path>
                  </svg>
                </template>
                <template v-if="card.rarity == 'Rare'">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
                    <path d="M12.842 12.005l4.03-4.03 4.031 4.03-4.03 4.03zM3.238 11.995l4.03-4.03 4.031 4.03-4.03 4.03z"></path>
                  </svg>
                </template>
                <template v-if="card.rarity == 'Epic'">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
                    <path d="M12.842 12.005l4.03-4.03 4.031 4.03-4.03 4.03zM8.035 16.802l4.03-4.03 4.031 4.03-4.03 4.03zM3.238 11.995l4.03-4.03 4.031 4.03-4.03 4.03z"></path>
                  </svg>
                </template>
                <template v-if="card.rarity == 'Legendary'">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path d="M12 0L0 12l12 12 12-12L12 0zm0 22.4L1.6 12 12 1.6 22.4 12 12 22.4z"></path>
                    <path d="M12.842 12.005l4.03-4.03 4.031 4.03-4.03 4.03zM8.045 7.198l4.03-4.03 4.03 4.03-4.03 4.03zM8.035 16.802l4.03-4.03 4.031 4.03-4.03 4.03zM3.238 11.995l4.03-4.03 4.031 4.03-4.03 4.03z"></path>
                  </svg>
                </template>
                {{ card.rarity }}
              </span>
              {{ card.name }}
            </span>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import rawCards from '~/calling-cards.json'

let i = 0;

const cards = rawCards.map((card: any) => {
  card.id = i++;
  return card;
});

export default Vue.extend({
  data () {
    return {
      rarities: [
        'Base',
        'Common',
        'Rare',
        'Epic',
        'Legendary'
      ],
    }
  },
  computed: {
    cards(): any[] {
      return cards.filter((card: any) => this.rarities.includes(card.rarity))
    }
  }
})
</script>

<style>
.rarity svg {
  width: .9em;
  height: .9em;
}
.rarity.base {
  color: #969b9c;
  fill: #969b9c;
}
.rarity.common {
  color: #7ba84f;
  fill: #7ba84f;
}
.rarity.rare {
  color: #6794ce;
  fill: #6794ce;
}
.rarity.epic {
  color: #c169f2;
  fill: #c169f2;
}
.rarity.legendary {
  color: #f47b12;
  fill: #f47b12;
}

.calling-card-container {
  border-bottom: 1px black solid;
  padding-top: 5px;
  padding-bottom: 5px;
}

.calling-card-banner {
  width: 100%;
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
