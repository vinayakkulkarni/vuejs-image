<template>
  <div class="ui form">
    <div class="field">
      <div v-if="!image">
        <img 
          src="https://placehold.it/180x180" 
          v-bind:alt="alt"
          v-bind:style="{'padding-bottom': paddingBottom}" 
          class="ui image" />
        <label :for="name" class="ui basic button">Select Image</label>
        <input type="file" :id="id" :name="name" style="display:none;" accept="image/*" @change="onFileChange">
      </div>
      <div v-else>
        <img 
          :src="image" 
          :alt="alt"
          :style="{'max-width': maxWidth, 'max-height': maxHeight, 'padding-bottom': paddingBottom}" 
          class="ui image" />
        <button class="ui basic button" @click="removeImage">Remove image</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      image: '',
    }
  }, 
  props: {
    id: {
      type: String,
      default: 'name'
    },
    name: {
      type: String,
      default: 'name'
    },
    alt: {
      type: String,
      default: 'Very Interesting Image'
    },
    maxWidth: {
      type: String,
      default: '200px'
    },
    maxWidth: {
      type: String,
      default: '200px'
    },
    paddingBottom: {
      type: String,
      default: '2px'
    }
  },
  methods: {
    onFileChange(e) {
      let files = e.target.files || e.dataTransfer.files;
      if (!files.length)
        return;
      this.createImage(files[0]);
    },
    createImage(file) {
      let image = new Image();
      let reader = new FileReader();
      let t = this;

      reader.onload = (e) => {
        t.image = e.target.result;
      };
      reader.readAsDataURL(file);
    },
    removeImage (e) {
      this.image = '';
    }
  }
}
</script>