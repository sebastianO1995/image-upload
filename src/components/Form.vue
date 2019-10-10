<template>
  <div>
    <h1>Please upload your images</h1>
    <div><input
        type="file"
        @change="fileChanged"
        multiple
      >
    </div>
    <div class="selected-images">
      <h2>You have selected:</h2>
      <ol>
        <li
          v-for="(image,index) in selectedImages"
          :key="index"
        >{{image.name}}</li>
      </ol>
      <button @click="upload">Upload Your Files</button>
    </div>

  </div>
</template>
<script>

export default {
  data () {
    return {
      selectedImages: []
    }
  },
  methods: {
    fileChanged (event) {
      console.log(event.target.files)
      this.selectedImages = event.target.files
    },
    upload () {
      const imageFormData = new FormData()
      // make axios call here
    }
  }

}
</script>
<style>
.selected-images {
  margin: 10px 20%;
}
button {
  margin-top: 5px;
  height: auto;
  color: white;
  background-color: blue;
  font-size: 20px;
  padding: 10px;
}

.selected-images ol{
  width: 50%;
  margin:  auto;
}
li {
  text-align: left;
  padding-bottom:10px;
}
</style>