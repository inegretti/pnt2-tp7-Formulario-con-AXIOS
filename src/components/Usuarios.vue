<template>

  <section class="src-components-http-client">
     <div class="jumbotron">
    <h1>Usuarios</h1>
    <button class="btn btn-success my-3 mr-3" @click="getPostsAxios()">Pedir por axios</button>
    <button class="btn btn-danger my-3 mr-3" @click="posts=[]">Clear</button>
    <br>
     <hr>
    <table v-if="posts.length" class="table table-dark">
      <tr>
        <th>Nombre</th>
        <th>Telefono</th>
        <th>Email</th>
      </tr>
      <tr v-for="(post,index) in posts" :key="index">
        <td>{{post.name}}</td>
        <td>{{post.edad}}</td>
        <td>{{post.emai}}</td>
      </tr>
    </table>
    <h2 v-else class="alert alert-danger text-center">no se encuentran datos</h2>
    </div>
  </section>

</template>

<script>

  export default  {
    name: 'src-components-http-client',
    props: [],
    mounted () {

    },
    data () {
      return {
        url:"https://634271f73f83935a78433ad7.mockapi.io/personas",
        posts:[ ],

      }
    },
    methods: {
      getPostsAxios(){
        this.axios(this.url).then(respuesta=>{this.posts=respuesta.data}).catch(error=>console.error(error))
      }
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
    .jumbotron{
    background-color: red;
    color: black;
  }
  hr{
    background-color: black;
  }
</style>
