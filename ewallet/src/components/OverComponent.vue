
<template>
    <section class="top">
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
          subTitle: 'Aktivt Kort',
          state: false
        },
        {
          name: 'AddCard',
          title: 'Nytt Kort',
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
    font-family: 'none';
    font-size: 32px;
    margin: 24px 0;
  }
  p {
    font-size: 0.8rem;
    color: rgb(0, 0, 0);
    font-weight: 600;
    margin: 4px 0;
  }
  h1, p {
    text-transform: uppercase;
  }
</style>