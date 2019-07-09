<template>
  <div>
    Email {{ email }}<br />
    Localidade {{ localidade }}
    <cc-button />
  </div>
</template>

<script>
import CcButton from '../Button'
import { mapActions } from 'vuex'

export default {
  name: 'CodecastApp',
  mounted() {
    const payload = {
      name: 'Diego',
      email: 'diego@gmail.com',
      level: 'usuario-raso',
      city: 'Santo André',
      state: 'SP'
    }
    setTimeout(() => {
      this.changeUser(payload)
    },3000)
    // Executa mutation

  },
  components: {
    CcButton
  },
  methods: {
    ...mapActions(['changeUser'])
  },
  computed: {
    email () {
      return this.$store.state.user.email
    },
    localidade () {
      return this.$store.getters.localidade
    }
  }
}
</script>
