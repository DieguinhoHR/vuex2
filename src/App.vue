<template>
  <div>
    <h1>Welcome Vue2</h1>
    <h4> {{ user }}</h4>

    <hr />

    <cc-users />
  </div>
</template>

<script>
import CcUsers from './components/users/Main.vue'
import { mapState } from 'vuex'

export default {
  components: {
    CcUsers
  },
  computed: {
    ...mapState({
      user: state => {
        const { name, email } = state.user

        return `o usuário logado é ${name} e possui o email ${email}`
      }
    })
    /* user () {
      const { name, email } = this.$store.state.user
      return `o usuário logado é ${name} e possui o email ${email}`
    } */
  }
}
</script>
