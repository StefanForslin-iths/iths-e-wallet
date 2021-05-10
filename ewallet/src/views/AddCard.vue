<template>
  <div>
    <header>
      <OverComponent />
    </header>
    <main>
      <Card v-bind:card="card" />
      <CardMod
        v-bind:card="card"
        v-on:addCard="pushCard()"
        />
    </main>
  </div>
</template>
<script>
import OverComponent from '@/components/OverComponent.vue'
import Card from '@/components/Card.vue'
import CardMod from '@/components/CardMod.vue'
export default {
  components: {
    OverComponent,
    Card,
    CardMod
  },
  data() {
    return {
      card: {
        holder: "",
        vendor: "",
        number: "",
        validMonth: "",
        validYear: "",
      }
  }},
  computed: {
    newCard() {
      return {
          id: Date.now(),
          holder: this.card.holder,
          vendor: this.card.vendor,
          number: this.card.number,
          validMonth: this.card.validMonth,
          validYear: this.card.validYear,
          active: false
      }
    },
  },
  methods: {
    pushCard() {
      this.$root.setAddCard(this.newCard)
    },
  },
}
</script>
<style>
</style>