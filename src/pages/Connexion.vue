<template>
      <h1>Connexion</h1>

  <section id="connexionStyle">
    <div class="background">
        <input class="connectionPlacement" v-model="pseudo" placeholder="Entrez votre pseudo" /> <br />
        <br />
        <input
          type="password"
          v-model="password"
          placeholder="Entrez votre mot de passe"
        />
        <br />
        <br />
        <button @click="saveConnexion">Connexion</button>
    </div>
  </section>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  name: 'ConnexionForm',
  data: function () {
    return {
      pseudo: '',
      pseudojuste: 'p',
      password: '',
    }
  },

  methods: {
    ...mapMutations(['setPseudo']),
    ...mapMutations(['setPassword']),
    saveConnexion() {
      if (
        this.pseudo == this.pseudojuste &&
        this.password == this.pseudojuste
      ) {
        alert('Bienvenue ! ')
        this.setPassword(this.password)
        this.setPseudo(this.pseudo)
      } else {
        alert('Utilisateur ou mot de passe inconnu')
      }
    },
  },
}
</script>

<style scoped>

.background {
  /*   C'est moche, à bosser*/
  height: 500px;
}

h1 {
  color: rgb(193, 162, 109);
}
.connectionPlacement{
  margin-top: 150px;
}
</style>
