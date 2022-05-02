<!-- Please remove this file from your project -->
<template>
  <section class="[ modal-container ] [  ]">
    <h1 class="sr-only">Rating Modal</h1>
    <div class="[ modal-content ]" v-if="!submitted">
      <div class="star-container">
        <img src="/icon-star.svg" alt="">
      </div>
      <h2>How did we do?</h2>
      <p>Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>
      <form action="">
        <fieldset>
          <input type="radio" name="rating" id="1" @change="updateRating">
          <label for="">1</label>
          <input type="radio" name="rating" id="2" @change="updateRating">
          <label for="">2</label>
          <input type="radio" name="rating" id="3" @change="updateRating">
          <label for="">3</label>
          <input type="radio" name="rating" id="4" @change="updateRating">
          <label for="">4</label>
          <input type="radio" name="rating" id="5" @change="updateRating">
          <label for="">5</label>
        </fieldset>
        <button type="submit" @click="modalSubmit" :disabled="rating==0">Submit</button>
      </form>
    </div>
    <div class="[ modal-content ]" v-else>
      <div class="image-container">
        <img src="/illustration-thank-you.svg" alt="">
      </div>
      <p class="you-selected">You selected {{ rating }} out of 5</p>
      <h2>Thank you!</h2>
      <p>We appreciate you taking the time to give a rating. If you ever need more support, don't hesitate to get in touch!</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Modal',
  data () {
    return {
      submitted: false,
      rating: 0
    }
  },
  methods: {
    modalSubmit(e) {
      this.submitted = !this.submitted
    },
    updateRating(e) {
      this.rating = Number(e.target.id)
    }
  }
}
</script>
