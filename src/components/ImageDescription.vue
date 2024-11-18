<template>
  <div class="description-overlay">
    <div class="description-content">
      <h3>Descripción</h3>
      <div class="description-grid">
        <div class="left-column">
          <img :src="photo.url" :alt="photo.description" />
          <p><strong>Autor:</strong> {{ photo.author }}</p>
          <button @click="$emit('close')">Cerrar</button>
        </div>
        <div class="right-column">
          <div class="description-box">
            <p><strong>{{ photo.title }}</strong></p>
            <p>{{ photo.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'ImageDescription',
    props: {
        photo: Object,
    },
    /* data: function(){
        return {}
    }, */
    // computed: {},
    //methods: {}
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
};
</script>

<style scoped>
.description-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
}
.description-content {
  background: white;
  padding: 20px;
  border-radius: 8px;
  text-align: left;
  max-width: 600px;
  width: 90%;
}
.description-content h3 {
  text-align: left;
}
.description-content img {
  max-width: 100%;
  height: auto;
  margin-bottom: 10px;
}
.description-content button {
  background-color: #f44336;
  color: white;
  border: none;
  border-radius: 8px;
  padding: 5px 10px;
  cursor: pointer;
  margin-bottom: 10px;
}
.description-grid {
  display: flex;
  gap: 20px;
}
.left-column {
  flex: 1;
  text-align: center;
}
.left-column img {
  max-width: 100%;
  height: auto;
  margin-bottom: 10px;
}
.left-column button {
  background-color: #f44336;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  margin-top: 10px;
}
.right-column {
  flex: 1;
}
.description-box {
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  padding: 10px;
  height: 200px;
  overflow-y: auto; /* Habilita el scroll vertical */
}
</style>