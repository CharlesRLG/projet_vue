<template>
  <div class="connexion">
    <div class="background">
      <div id="body_contact">
        <div id="corp">
          <div id="corp_partie_2">
            <div id="presentation_connection">
              <div id="formulaire_connection">
                <h1>Connexion</h1>
                <label for="pseudo">Pseudo</label>
                <input v-model="pseudo" />
                <br>
                <label for="password">Mot de passe</label>
                <input type="password" v-model="password" />
                <button @click="saveConnexion">Connexion</button>
              </div>
              <div id="si_probleme_connection">
                <div>
                    <h3>En cas de problème, veuiller appeler le numéro suivant :</h3>
                </div>
                <div>
                    <p>1010011 1001111 1010011</p>
                </div>
                <div>
                    <h3>Ou à l'adresse mail suivant :</h3>
                </div>
                <div>
                    <p>pasDeBol@lapoisse.com</p>
              </div>
              </div>
            </div>
          </div>
        </div>
      </div> 
    </div>         
  </div>
</template>
  

<script>
import { mapMutations } from "vuex";
export default {
  name: 'ConnexionForm',
  data: function() {
    return {
      pseudo: "",
      pseudojuste:"plop",
      password: "",
    }
  },
  methods: {
    
    ...mapMutations(["setPseudo"]),
    ...mapMutations(["setPassword"]),
    saveConnexion() {
        if(this.pseudo == this.pseudojuste && this.password == this.pseudojuste){
          alert("bien joué")
          this.setPassword(this.password);
          this.setPseudo(this.pseudo);
        }else{
          alert("tu es mauvais")
        }
        
    }
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400&display=swap%22");
@media screen and (min-width:800px){
    #body_contact {
        display: flex;
        justify-content:center;
    }
    h1, h2, h3, h4, p {
    font-family: "Oswald", sans-serif;
    color: #232a3d;
    }
 /* carré/borture extérieur du corp */
    #corp {
    width: 95%;
    margin-top: 5px;
    background-color: #232a3d;
    opacity: 0.90;
    border:solid 1px #92a5da;
    border-radius: 5px;
    }
 /* carré/borture intérieur du corp   */
    #corp_partie_2 {
    margin: 5px;
    background: rgba(238, 223, 210, 0.8);
    border:solid 1px #ED9544;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    align-items: center;
    }
    #presentation_connection {
    display: flex;
    flex-direction: column;
    align-items: center;
    }
        #presentation_connection {
    display: flex;
    flex-direction: column;
    align-items: center;
    }
        #si_probleme_connection {
    color: #e7edfc;
    margin: 10px 20%;
    text-align: center;
    }
}
@media screen and (min-width:340px) and (max-width:799px) {
    #body_contact {
      display: flex;
      justify-content:center;
    }
    h1, h2, h3, h4, p {
      font-family: "Oswald", sans-serif;
      color: #232a3d;
    }
 /* carré/borture extérieur du corp */
    #corp {
      width: 60%;
      min-width: 400px;
      margin-top: 5px;
      background-color: #232a3d;
      opacity: 0.90;
      border:solid 1px #92a5da;
      border-radius: 5px;
    }
 /* carré/borture intérieur du corp   */
    #corp_partie_2 {
    margin: 5px;
    background: rgba(238, 223, 210, 0.8);
    border:solid 1px #ED9544;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    align-items: center;
    }
    #presentation_connection {
    display: flex;
    flex-direction: column;
    align-items: center;
    }
        #presentation_connection {
    display: flex;
    flex-direction: column;
    align-items: center;
    }
    #si_probleme_connection {
    color: #e7edfc;
    margin: 10px 20%;
    text-align: center;
    }
}
</style>