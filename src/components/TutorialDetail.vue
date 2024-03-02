<template>
    <div v-if="guncellenecekTutorial" class="submit-form">
        <div class="form-group">
            <label for="title" >Başlık : </label>
            <input type="text" 
            class="form-control"
             id="title" required 
             v-model="guncellenecekTutorial.title"
             name="title" />
        </div>
        <div class="form-group">
            <label for="description" >Açıklama : </label>
            <input type="text" 
            class="form-control"
             id="description" 
              v-model="guncellenecekTutorial.description"
            required name="description" />
        </div>
        <br />
        
    </div>
</template>
<script>
import TutorialDataService from "../services/TutorialDataService"
export default {
    name : "tutorial-detail",
    data(){
        return{
            guncellenecekTutorial : null,
        }
    },
    methods: {
      tutorialDetayGetir(id){
        TutorialDataService.getTutorialDetail(id).then(gelenTutorial => {
            //{"id":id,"title":"testtest","description":"testtestdesc","published":false}
            this.guncellenecekTutorial = gelenTutorial.data;
        })
      }
    },
    mounted() {
        //bana bir önceki yani tutoriaListteki tıklamış olduğum tutorial ın id si gelecek
        this.tutorialDetayGetir(this.$route.params.id);
    }
    
}
</script>