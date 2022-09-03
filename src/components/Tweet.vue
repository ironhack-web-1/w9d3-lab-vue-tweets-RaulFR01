<template>
  <div className="tweet">
    <ProfileImage :src="contentImage" />
    <div className="body">
      <div className="top">
        <span className="user">
          <span className="name">{{ contentName }}</span>
          <span className="handle">{{ contentHandle }}</span>
        </span>

        <span className="timestamp">{{ contentTime }}</span>
      </div>

      <p className="message">{{ mensaje }}</p>

      <div className="actions">
        <!-- Font Awesome icons -->
        <i class="far fa-comment"></i>
        <i class="fas fa-retweet"></i>
        <i class="far fa-heart"></i>
        <i class="fas fa-share"></i>
      </div>
    </div>

    <i class="fas fa-ellipsis-h"></i>
  </div>
</template>

<script>
import ProfileImage from "./ProfileImage.vue";
export default {
  data() {
    return {
      contentName: null,
    };
  },
  props: {
    contentName: {
      type: String,
    },
    contentImage: {
      type: String,
      default: `data:image/jpeg;base64,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`,
    },
    contentHandle: {
      type: String,
    },
    contentTime: {
      type: String,
    },
    mensaje: {
      type: String,
      default: "hohlhorkelrkedklgklrek",
    },
  },
  components: { ProfileImage },
};
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
