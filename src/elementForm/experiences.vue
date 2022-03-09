  <template>
    <div class="Experiences">
      <h1>Expérience</h1>
        <div>
            <p>Nom</p>
            <input v-model="experienceChamps.nomExperience" />
            <br>
            <p>Date de début</p>
            <input v-model="experienceChamps.dateDeDebutExperience" type="date"/>
            <br>
            <p>Date de fin</p>
            <input v-model="experienceChamps.dateDeFinExperience" type="date"/>
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
            experienceChamps: [{
              nomExperience: "", 
              dateDeDebutExperience: "", 
              dateDeFinExperience: ""
            }],
            experienceTabs: [
              {nomExperience: "ex: caissier", 
              dateDeDebutExperience: "ex: 14/14/56", 
              dateDeFinExperience: "ex: 42/42/42"},
            ]
          }
        },

      methods: {
        saveExperience: function () {
          this.experience = Object.assign({}, this.experienceChamps);
          // alert('vous avez une nouvelle expérience' + this.experience.nomExperience)

          this.experienceTabs.push(this.experience);
          alert('vous avez une nouvelle formation'+this.experienceTabs.nomExperience)
    },
  },
}
</script>