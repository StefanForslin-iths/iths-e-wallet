
<template>
  <div class="home">
    <header>
      <OverComponent />
    </header>
    <main>
      <div 
          @mouseover="hovering" 
          @mouseout="hovering"
          >
          <div
          :class="{ rmbutton: isHovering }"
          @click="deleteCard()">
          </div>
        <Card  
          v-bind:card="activeCard"
        />
      </div>
      <CardSource v-bind:cards="cards" />
    </main>
  </div>
</template>
<script>
import OverComponent from '@/components/OverComponent.vue'
import Card from '@/components/Card.vue'
import CardSource from '../components/CardSource.vue'
export default {
  name: 'Home',
  components: {
    OverComponent, Card,
    CardSource,
  },
  data() {return {
    isHovering: false
  }},
  computed: {
    cards() {
      return this.$root.cards
    },
    activeCard() {
      return this.cards.find(card => card.active === true); 
    },
  },
  methods: {
    hovering() {
      this.isHovering = !this.isHovering
    },
    deleteCard() {
      this.$root.setDeleteCard()
    }
  }
}
</script>
<style scoped>
/* Delete btn */
  .rmbutton {
    position: relative;
  }
  .rmbutton::before {
    content: '';
    position: absolute;
    background-color: rgb(70, 69, 69);
    opacity: 0.8;
    width: 32px;
    height: 32px;
    right: -10px;
    top: -10px;
    border-radius: 100%;
    cursor: pointer;
  }
  .rmbutton::after {
    content: 'x';
    position: absolute;
    font-size: 24px;
    right: -1.75px;
    top: -1.5px;
    color: #fff;
    line-height: 50%;
    cursor: pointer;
  }
</style>