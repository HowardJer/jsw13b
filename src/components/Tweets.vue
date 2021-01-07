<template>
  <div>
    <button @click="notifyParent">display tweets</button>
    <br />
  </div>
</template>

<script>
export default {
  name: "vue-tweets",
  data() {
    return {
      tweets: [
        {
          author: "Man with no shoes",
          date: "06/15/20",
          text: "I bought new shoes today",
        },
        {
          author: "Grim Reaper",
          date: "07/15/20",
          text: "Time is tioght",
        },
        {
          author: "Carlos Santana",
          date: "08/15/20",
          text: "Samba Pa Ti",
        },
        {
          author: "Justin Hayward",
          date: "09/15/20",
          text: "'So they gave it a word'",
        },
        {
          author: "Kahlil Gibran",
          date: "10/15/20",
          text: "Empty and dark shall I raise my Lantern",
        },
        {
          author: "William Shakespeare",
          date: "11/15/20",
          text: "Let he who hath steerage of my course",
        },
      ],
    };
  },
  methods: {
    notifyParent: function () {
      this.$emit("tweetContent", this.tweets);
    },
  },
};
</script>

<style>
</style>