<template>
  <div id="videoPreview" class="text-center container pt-16 pa-4">
    <div v-if="contentType == 'slide'">
      <pdf
        :src="link"
        @num-pages="pageCount = $event"
        @page-loaded="loadFile"
        v-for="i in currentPage"
        :key="i"
        width="100%"
        :page="i"
      ></pdf>
    </div>

    <div v-else-if="contentType == 'video'">
      <iframe
        v-if="link.split(':')[0] != 'data'"
        id="video"
        width="96%"
        height="496px"
        :src="link + '?autoplay=1'"
      >
      </iframe>

      <video
        v-else
        width="100%"
        id="video-preview"
        controls
        autoplay
        :src="link"
      />
    </div>

    <div v-else-if="contentType == 'form'">
      <iframe id="video" width="100%" height="600px" :src="link"> </iframe>
    </div>

    <vue-calendly
      v-else-if="contentType == 'calender'"
      :url="link"
      :height="600"
    ></vue-calendly>
  </div>
</template>

<script>
import pdf from "vue-pdf";

export default {
  components: {
    pdf,
  },
  props: ["link", "contentType"],
  data() {
    return {
      currentPage: 1,
      pageCount: 0,
    };
  },
  methods: {
    loadFile() {
      this.currentPage++;
    },
  },
  created() {
    if (this.link == undefined) this.$router.push({ name: "Home" });
  },
};
</script>

<style scoped>
#video,
#video-preview {
  border-radius: 7px;
  border: none;
}
</style>


