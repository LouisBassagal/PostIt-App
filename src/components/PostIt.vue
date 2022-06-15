<template>
  <link rel="stylesheet" type="text/css" href="//fonts.googleapis.com/css?family=Nobile"/>
  <div class="UserInput">
    <ul class="UserInputList">
      <la>
        <p class="UserInput">Titre du PostIt :</p>
          <input class="UserInput" v-model="NewTitle" type="text" name="model"/>
      </la>
      <la>
        <p class="UserInput">Description :</p>
        <input class="UserInput" v-model="NewPostIt" type="text" name="model"/>
      </la>
      <la>
        <br/>
        <button class="UserInput" @click=AddPostIt>Add PostIt</button>
      </la>
    </ul>
  </div>
  <ul class="DisplayPostIts">
    <la v-for="postit in PostIts" :key=postit.id>
      <div class="PostIts">
        <h1 class="DisplayPostIt">{{ postit.Title }}</h1>
        <p class="DisplayPostIt">{{ postit.PostIt }}</p>
      </div>
    </la>
  </ul>
</template>

<script>
let id = 0;

export default {
  data() {
    return {
      NewTitle: '',
      NewPostIt: '',
      PostIts: [
        { id: id++, Title: "Tmp", PostIt: "Tmp" }
      ]
    }
  },
  methods: {
    AddPostIt() {
      if (!this.NewPostIt || !this.NewTitle) {
        throw new TypeError("You must enter a title and a postit");
      } else {
        this.PostIts.push({ id: id++, Title: this.NewTitle, PostIt: this.NewPostIt });
        this.NewTitle = '';
        this.NewPostIt = '';
      }
    }
  }
}
</script>

<style scoped>
.PostIts {
  margin: auto;
  text-align: center;
  overflow: visible;
  background-color: #fff;
  height: 350px;
  width: 350px;
  color: #454;
  font-family: "Nobile";
  background-color: yellow;
  border-radius: 10px;
  box-shadow: 0px 10px 10px;
}
.DisplayPostIts {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between
}
h1.DisplayPostIt {
  margin-left: 20px;
  text-align: left;
}
p.DisplayPostIt {
  margin-left: 20px;
  text-align: center;
  overflow: hidden;
  white-space: pre;
  text-overflow: ellipsis;
}
p.UserInput {
  text-align: center;
  line-break: loose;
}
</style>
