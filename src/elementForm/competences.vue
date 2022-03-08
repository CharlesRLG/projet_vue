  <template>
    <div class="Compétences">
      <h1>Compétences</h1>
        <div>
            <p>Nom</p>
            <input v-model="competenceTabsNews.nomCompetence" />
            <br>
            <button @click="saveCompetence()">Enregistrer</button>
        </div>
        <div>
            <table>
            <thead>
                <tr>
                    <th>Nom </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="competenceTab in competenceTabs" :key="competenceTab">
                    <td>{{competenceTab.nomCompetence}}</td>
                </tr>
            </tbody>
            </table>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
          return {
            competence:[],
            competenceTabsNews: [{
              nomCompetence: "", 
            }],
            competenceTabs: [
              {nomCompetence: "ex: caissier",
            }]
          }
        },

      methods: {
        saveCompetence: function () {
          this.competence = Object.assign({}, this.competenceTabsNews);
          // alert('vous avez une nouvelle expérience' + this.experience.nomExperience)

          this.competenceTabs.push(this.competence);
          alert('vous avez une nouvelle compétence '+this.competenceTabs.nomCompetence)
    },
  },
}
</script>