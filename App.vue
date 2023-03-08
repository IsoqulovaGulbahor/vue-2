<template>
  <div>
    <p>full name :{{ fullName }}</p>
    <p>
      <label for="firstName">first name:</label>
      <input type="text" id="firstName" v-modul="firstName" />
    </p>
    <p>
      <label for="lastName">first name:</label>
      <input type="text" id="lastName" v-modul="firstName" />
    </p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      firstName: "",
      lastName: "",
    };
  },
  computed: {
    fullName() {
      return this.firstName + " " + this.lastName;
    },
  },
};
</script>
<style lang=""></style>

<template>
  <div id="app">
    <input type="text" v-modul="seachQuary" placeholder="Search" />
    <li v-for="book in filterBookByName" :key="book.id">
      Book title: {{ book.title }} - Author {{ book.author }}
    </li>
  </div>
</template>
<script>
export default {
  data() {
    return {
      book:[ {
        id:1,
        title:"O'tgan kunlar",
        author:"O'tkir hoshimov"
      },
      {
        id:2,
        title:"Xamsa",
        author:"Alisher Navoiy"
      },
      {
        id:3,
        title:"Boburnoma",
        author:"Z.M.Bobur"  
      },
    ],
    };
  },
  computed: {
    filterBookByName:function() {
      return this.book.filter((book => !book.title.toLowerCase().indexOf(this.seachQuary.toLowerCase()));
      
    },
  },
};
</script>
<style lang=""></style>
