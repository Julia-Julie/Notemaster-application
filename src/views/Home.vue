<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->

    <div class="container">
      <div class="home__content">
      <h1>{{ headline }}</h1>

      <div class="home__field">
        <label for="home-title">Title</label>
        <input type="text" id="home-title" v-model="note.title" />
      </div>

      <div class="home__field">
        <label for="home-text">Text</label>
        <textarea id="home-text" v-model="note.text"></textarea>
      </div>

      <button class="btn-primary" @click="addNote">Submit</button>
    </div>
    </div>

    
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {
    // HelloWorld
  },

  data() {
    return {
      headline: "Notemaster application",
      note: {
        title: "",
        text: "",
      },

      notes: [
        {
          title: 'Do shopping',
          text: 'Buy bread, eggs and sausages',
          date: new Date(Date.now)

        }
      ]
    };
  },

  methods:{
    addNote(){
      let {title, text} = this.note
      this.notes.push({
        text,
        title, 
        date: new Date(Date.now)
      })
    }
  }
};
</script>

<style scoped lang="scss">
input,
select,
textarea,
button,
::placeholder {
  all: unset;
}

.container{
  max-width: 1100px;
  margin: 0 auto;
}

.home {
  background-color: rgb(228, 247, 250);
  display: flex;
  justify-content: center;

  &__content {
    // max-width: 800px;
    min-width: 600px;
    border: 1px solid green;
  }

  &__field {
    margin-bottom: 2rem;
    padding: 10px;
    display: flex;
    flex-direction: column;

    label{
      font-size: 2rem;
      font-weight: bold;
      color: violet;
      text-align: left;
      padding-bottom: 10px;
    }
    
    input, textarea{
    border: 1px solid grey;
    padding: 1rem;

    }

    > *{
      display: block;
    }
  }

  .btn-primary{
    background-color: violet;
    padding: 16px 48px;
    border-radius: 10px;
    font-size: 1.3rem;
    margin-bottom: 2rem;
    transition: all .3s ease;
    cursor: pointer;

    &:hover{
      background-color: rgb(250, 245, 235);
      color: violet;
      border: 1px solid grey;
      box-shadow: 0px 0px 2px #ccc;
    }
  }
}
</style>
