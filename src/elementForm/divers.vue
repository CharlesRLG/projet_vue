  <template>
    <div class="Divers">
      <h1>Divers</h1>
        <div>
            <p>Nom</p>
            <input v-model="diversTabsNews.nomDivers" />
            <br>
            <button @click="saveDivers()">Enregistrer</button>
        </div>
        <div>
            <table>
            <thead>
                <tr>
                    <th>Nom</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="diversTab in diversTabs" :key="diversTab">
                    <td>{{diversTab.nomDivers}}</td>
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
            divers:[],
            diversTabsNews: [{
              nomDivers: "", 
            }],
            diversTabs: [
              {nomDivers: "ex: Lecture", }
            ]
          }
        },

      methods: {
        saveDivers: function () {
          this.divers = Object.assign({}, this.diversTabsNews);
          // alert('vous avez une nouvelle expérience' + this.experience.nomExperience)

          this.diversTabs.push(this.divers);
          alert('vous avez une nouvelle activité diver:' + this.diversTabs.nomDivers)
    },
  },
}
</script>