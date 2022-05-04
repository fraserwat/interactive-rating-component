<!-- Please remove this file from your project -->
<template>
  <section class="[ modal ] [ bg-black-gradient ]">
    <h1 class="sr-only">Rating Modal</h1>
    <div class="[ modal-content ] [ flow flex-col pad-top-600 pad-bottom-600 pad-right-600 pad-left-600 ]" v-if="!submitted">
      <div class="[ star-container ] [ circular flex-row flex-center ]">
        <img src="/icon-star.svg" alt="" aria-hidden="true">
      </div>
      <h2 class="font-white">How did we do?</h2>
      <p class="font-light-grey">Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>
      <form class="flow">
        <fieldset class="flex-row space-between">
          <input type="radio" name="rating" id="1" @change="updateRating">
          <label for="1" class="[ circular flex-row flex-center ]">1</label>
          <input type="radio" name="rating" id="2" @change="updateRating">
          <label for="2" class="[ circular flex-row flex-center ]">2</label>
          <input type="radio" name="rating" id="3" @change="updateRating">
          <label for="3" class="[ circular flex-row flex-center ]">3</label>
          <input type="radio" name="rating" id="4" @change="updateRating">
          <label for="4" class="[ circular flex-row flex-center ]">4</label>
          <input type="radio" name="rating" id="5" @change="updateRating">
          <label for="5" class="[ circular flex-row flex-center ]">5</label>
        </fieldset>
        <button type="submit" @click="modalSubmit" :disabled="rating==0" class="[ modal-button ] [ bg-orange font-white ]">Submit</button>
      </form>
    </div>
    <div class="[ modal-content ] [ flow flex-col flex-center pad-top-700 pad-bottom-700 pad-right-700 pad-left-700 ]" v-else>
      <div class="image-container">
        <img src="/illustration-thank-you.svg" alt="Phone paying transaction">
      </div>
      <p class="[ modal-rating-text ] [ bg-dark-blue font-orange ]">You selected {{ rating }} out of 5</p>
      <h2 class="[ font-white ]">Thank you!</h2>
      <p class="[ align-center font-light-grey ]">We appreciate you taking the time to give a rating. If you ever need more support, don't hesitate to get in touch!</p>
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
