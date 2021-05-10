<template>
    <section class="top">
      <header>
        <h1> {{ title }} </h1>
      </header>
      <p> {{ subTitle }} </p>
    </section>
</template>
<script>
export default {
  beforeMount() {
    this.title = this.topPage.title
    this.subTitle = this.topPage.subTitle
    this.topPage.state = true
  },
  data() {
    return {
      title: '',
      subTitle: '',
      topData: [
        {
          name: 'Home',
          title: 'Ewallet',
          subTitle: 'Aktivt Kort',
          state: false
        },
        {
          name: 'AddCard',
          title: 'Lägg till nytt kort',
          subTitle: 'Kort',
          state: false
        }
      ],
    }
  },
  computed: {
    currentPage() {
      return this.$route.name
    },
    topPage() {
      return this.topData.find(element => element.name === this.currentPage)
    }
  },
}
</script>
<style scoped>
  section {
    text-align: center;
  }
  h1 {
    font-family: 'Source Sans Pro';
    font-size: 32px;
    margin: 24px 0;
  }
  p {
    font-size: 0.8rem;
    color: rgba(0,0,0,.4);
    font-weight: 600;
    margin: 4px 0;
  }
  h1, p {
    text-transform: uppercase;
  }
</style>