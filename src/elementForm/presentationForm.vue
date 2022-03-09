<template>
    <div class="Presentation">
      <h1>Présentation</h1>
        <div>
            <p>Prénom</p>
            <input v-model="presentationTabsNews.prenomPresentation" />
            <br>
            <p>Nom</p>
            <input v-model="presentationTabsNews.nomPresentation" />
            <br>
            <p>Description</p>
            <textarea v-model="presentationTabsNews.descriptionPresentation" />
            <br>
            <button @click="savePresentation()">Enregistrer</button>
        </div>
        <div>
            <table>
            <thead>
                <tr>
                    <th>Prénom </th>
                    <th>Nom </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="presentationTab in presentationTabs" :key="presentationTab">
                    <td>{{presentationTab.prenomPresentation}}</td>
                    <td>{{presentationTab.nomPresentation}}</td>
                    <td>{{presentationTab.descriptionPresentation}}</td>
                </tr>
            </tbody>
            </table>
        </div>
    </div>
</template>
<script>
import { mapMutations } from 'vuex'
    export default {
        data() {
          return {
            presentation:[],
            presentationTabsNews: [{
              prenomPresentation: "", 
              nomPresentation: "", 
              descriptionPresentation: "",
            }],
            presentationTabs: [
              {prenomPresentation: "ex: Chandler", 
              nomPresentation: "ex: Bing", 
              descriptionPresentation: "ex: Plopi Plopi Plopi Plopi Plopi",
              },
            ]
          }
        },

      methods: {
    ...mapMutations(['setPresentation']),
    savePresentation() {
      if (!this.prenomPresentation &&
          !this.nomPresentation &&
          !this.descriptionPresentation 
      ) {
        alert('Attention, vous devez compléter tous les champs')
      } else {
        alert(
          'vous avez saisie : ' +
            this.prenomPresentation +
            this.nomPresentation +
            this.descriptionPresentation 
        )
        this.setPresentation(
            this.prenomPresentation &&
            this.nomPresentation &&
            this.descriptionPresentation
        )
      }
      // si présentation complet -> par le biais watch il va mapstate expérience
    },
  //       savePresentation: function () {
  //         this.presentation = Object.assign({}, this.presentationTabsNews);
  //         alert('vous vous appelez: ' + this.presentation.prenomPresentation)

  //         this.presentationTabs.push(this.presentation);
  //         alert('vous avez une nouvelle formation'+this.formationTabs.nomFormation)
  //   },
  },
}
</script>