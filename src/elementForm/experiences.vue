  <template>
    <div class="Experiences">
      <h1>Expérience</h1>
        <div>
            <p>Nom</p>
            <input v-model="experienceTabsNews.nomExperience" />
            <br>
            <p>Date de début</p>
            <input v-model="experienceTabsNews.dateDeDebutExperience" />
            <br>
            <p>Date de fin</p>
            <input v-model="experienceTabsNews.dateDeFinExperience" />
            <br>
            <button @click="saveExperience()">Enregistrer</button>
        </div>
        <div>
            <table>
            <thead>
                <tr>
                    <th>Nom </th>
                    <th>Date de début </th>
                    <th>Date de fin </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="experienceTab in experienceTabs" :key="experienceTab">
                    <td>{{experienceTab.nomExperience}}</td>
                    <td>{{experienceTab.dateDeDebutExperience}}</td>
                    <td>{{experienceTab.dateDeFinExperience}}</td>
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
            experience:[],
            experienceTabsNews: [{
              nomExperience: "", 
              dateDeDebutExperience: "", 
              dateDeFinExperience: ""
            }],
            experienceTabs: [
              {nomExperience: "caissier", 
              dateDeDebutExperience: "14/14/56", 
              dateDeFinExperience: "42/42/42"},
            ]
          }
        },

      methods: {
        saveExperience: function () {
          this.experience = Object.assign({}, this.experienceTabsNews);
          // alert('vous avez une nouvelle expérience' + this.experience.nomExperience)

          this.experienceTabs.push(this.experience);
          alert('vous avez une nouvelle formation'+this.experienceTabs.nomExperience)
    },
  },
}
</script>