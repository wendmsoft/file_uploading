<template>
  <v-container>
    <div class="mt-10">
      <!-- <iframe
        frameborder="0"
        allowfullscreen
        contain
        width="100%"
        height="496px"
        id="video-preview"
        controls
        src="https://www.youtube.com/embed/jDF92GUmM_s"
      /> -->

      <video
        contain
        width="100%"
        id="video-preview"
        controls
        src="../assets/welcome.mp4"
      />

      <v-layout row wrap class="mr-2">
        <v-flex xs12 md4 class="pt-13">
          <v-layout row wrap>
            <v-flex xs3 md2 class="text-center">
              <v-btn text>
                <v-icon>web</v-icon>
              </v-btn>
            </v-flex>
            <v-flex xs3 md2 class="text-center">
              <v-btn text>
                <v-icon>telegram</v-icon>
              </v-btn>
            </v-flex>
            <v-flex xs3 md2 class="text-center">
              <v-btn text>
                <v-icon>pan_tool</v-icon>
              </v-btn>
            </v-flex>
            <v-flex xs3 md2 class="text-center">
              <v-btn text>
                <v-icon>help_outline</v-icon>
              </v-btn>
            </v-flex>
          </v-layout>
        </v-flex>

        <v-flex xs3 md2 class="mt-10 pl-2">
          <v-btn text>
            <v-icon>keyboard_backspace</v-icon>
          </v-btn>
        </v-flex>

        <v-flex xs3 md2 class="mt-10">
          <span>Welcome</span>
        </v-flex>
        <v-flex xs3 md2 class="mt-10">
          <v-btn text>
            <v-icon>east</v-icon>
          </v-btn>
        </v-flex>

        <v-flex xs3 md2 class="mt-10 text-center">
          <v-btn small text class="orange">
            <span class="text-capitalize">Join waitlist</span>
          </v-btn>
        </v-flex>
      </v-layout>
    </div>
  </v-container>
</template>

<script>
export default {
  data: () => ({}),
};
</script>

<style scoped>
#video-preview {
  border-radius: 7px;
  border: none;
}
</style>