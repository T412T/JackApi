<template>
  <div class="fond" style="padding-top: 50px">
      <span> C:\User: cd Jack </span><br><br>
      <span> C:\User\Jack: run JackApi.exe </span><br><br>
      <span> C:\User\Jack: server JackApi v1.9.18.4 running on http://localhost:8080/</span>
        <div v-for="element in results" :key="element.id" >
            <br>
            <br>
            <span class="boldRed">C:\User\Jack\Id:  </span><span class="text">{{ element.id }}</span>
            <br>
            <br>
            <span class="boldRed"> C:\User\Jack\Type:  </span><span class="text">{{ element.type }}</span>
            <br>
            <br>
            <span class="boldRed"> C:\User\Jack\Joke:  </span><span class="text">{{ element.setup }}</span>
            <br>
            <br>
            <span class="boldRed"> C:\User\Jack\Punchline:  </span><span class="text">{{ element.punchline }}</span>
            <br>
            <br>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        name: "Joke",
        data(){
            return{
                results: []
            }
        },
        methods: {
            getMyJoke(){
                axios.get('https://official-joke-api.appspot.com/jokes/programming/ten')
                .then((joke) => {
                    console.log(joke.request.response);
                    this.results = JSON.parse(joke.request.response)
                })
                .catch(() => {
                    this.results = "PAS DE JOKE JE SUIS LA TRISTESSE";
                })
            }
        },
        mounted: function () {
            this.getMyJoke()
        }
    }
</script>

<style>
    .fond{
        background-color: #000000 ;
        background-repeat: no-repeat;
        text-align: left;
        
        
    }
</style>