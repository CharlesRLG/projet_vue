  <template>
    <div class="Formations">
      <h1>Formulaire</h1>
      <div>
        <p>Nom de la formation</p>
        <input v-model="formationTabsNews.nomFormation" />
        <br>
        <p>Date de début</p>
        <input v-model="formationTabsNews.dateDebutFormation" type="date"/>
        <br>
        <p>Date de fin</p>
        <input v-model="formationTabsNews.dateFinFormation" type="date"/>
        <br>
        <button @click="saveFormation()">Enregistrer</button>
      </div>
      <table>
        <thead>
            <tr>
                <th>Nom de la formation </th>
                <th>Début de la formation </th>
                <th>Fin de la formation </th>
            </tr>
        </thead>
        <tbody>
          <tr v-for="formationTab in formationTabs" :key="formationTab">
              <td>{{formationTab.nomFormation}}</td>
              <td>{{formationTab.dateDebutFormation}}</td>
              <td>{{formationTab.dateFinFormation}}</td>
          </tr>
        </tbody>
      </table>
      </div>
</template>

<script>
  export default {
      data() {
        return {
          formation:[],
          formationTabsNews: [{
            nomFormation: "", 
            dateDebutFormation: "", 
            dateFinFormation: ""
          }],
          formationTabs: [
            {nomFormation: "ex: Chandler Bing", 
            dateDebutFormation: "ex: 42/42/42", 
            dateFinFormation: "ex: 42/42/42"
            },
          ]
        }
      },

    methods: {
      saveFormation: function() {
        this.formation = Object.assign({}, this.formationTabsNews);
        alert('vous avez une nouvelle formation'+this.formation.nomFormation)

        this.formationTabs.push(this.formation);
        // alert('vous avez une nouvelle formation'+this.formationTabs[0].nomFormation)
    },
  },
}
</script>