<template>
  <section>
    <h1>Pricing page </h1>
    <CompanyHelper />
    <CityHelper />
    <ProductSelector v-if="signupCity" @product-chosen="onProductChosen"/>
  </section>
</template>

<script>
import {mapGetters} from 'vuex'
import CityHelper from "~/components/City/CityHelper";
import ProductSelector from "~/components/Product/ProductSelector";
import CompanyHelper from "~/components/Company/CompanyHelper";

export default {
  name: "pricing",
  components: {CompanyHelper, ProductSelector, CityHelper},
  computed: {
    ...mapGetters({
      signupCity: 'signup/city',
    })
  },
  methods: {
    onProductChosen() {
      this.$signupFlow.toNextStep(this.$route.name)
    }
  }
}
</script>

<style scoped>

</style>
