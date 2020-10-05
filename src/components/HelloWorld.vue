<template>
  <div class="assign">

    <h1>Demonstration of directives and data binding</h1>
    <h2>Book List</h2>
   <div class="bookList"> 
       <table>
         <tr>
           <th>
             Title
           </th>
           <th>Publication Year</th>
         </tr>
         <tr v-for="book in bookDetails">
           <td>{{book.title}} </td>
           <td>{{book.publication}}</td>
         </tr>
       </table>
   </div>
   <div class="addBookList">
     Enter Book Title:- <input type="text" v-model="bookTitle" />
     Enter Publication Year <input type="text" v-model="publicationYear" />
   </div>
   <div class="addBook">
     <button @click="addBook">
       Add Book
     </button>
   </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',

  data(){

    return {
      bookDetails:[
        {
        title :'MongoDB in Action',
        publication:'2011'
        },
        {
          title:'JavaScript: The Good Parts',
          publication:'2008'
        }
      ],
      bookTitle:'',
      publicationYear:'',
    }
  },
  methods:{
    addBook(){
      console.log("hello HelloWorld");
      this.bookDetails.push({
        title:this.bookTitle,
        publication:this.publicationYear
      })
      this.bookTitle= '';
      this.publicationYear='';
    }
  }
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
table,th,td {
  border : 1px solid black;
}
.bookList, .addBookList {
  margin-bottom :20px;
}
</style>
