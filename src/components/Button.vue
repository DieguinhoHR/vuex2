<template>
  <div>
    <button :disabled="!hasUser" @click="mudarDados">
      Mudar dados do usuário
    </button>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex'

export default {
  name: 'Botão',
  methods: {
    mudarDados () {
      const payload = {
        name: 'Outro nome',
        email: 'email@email.com',
        level: 'usuario-raso',
        city: 'Santo André',
        state: 'SP'
      }
      // Executa mutation
      this.changeUser(payload)
    },
    ...mapActions(['changeUser'])
  },
  computed: {
    hasUser () {
      return this.$store.state.user.name !== ''
    }
  }
}
</script>

<style>

</style>
