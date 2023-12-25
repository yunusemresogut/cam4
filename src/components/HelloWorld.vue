<script>

export default {
  data() {
    return {

    }
  },
  mounted() {
    this.startMedia()
  },
  methods: {
    startMedia: async () => {
      try {
        // Kullanıcının kamerasına ve mikrofonuna erişim izni istenir
        const stream = await navigator.mediaDevices.getUserMedia({ video: true, audio: true });

        // Video elementine stream atanır
        const localVideo = document.getElementById('localVideo');
        localVideo.srcObject = stream;
      } catch (error) {
        console.error('Error accessing media devices: ', error);
      }
    }
  }
}
</script>

<template>
  <h1>cam4</h1>
  <video id="localVideo" autoplay playsinline></video>
  <button @click="startMedia()">Başlat</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
