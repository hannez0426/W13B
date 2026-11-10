
<template>
  <section>
    <div class="toolbar">
      <h2>Latest Tweets</h2>

      <button @click="toggleView">
        {{ isGridView ? "☰ List View" : "▦ Card View" }}
      </button>
    </div>

    <div
      class="tweet-container"
      :class="{ 'grid-view': isGridView, 'list-view': !isGridView }"
    >
      <TweetCard
        v-for="tweet in tweets"
        :key="tweet.id"
        :tweet="tweet"
      />
    </div>
  </section>
</template>

<script>
import TweetCard from "./TweetCard.vue";

export default {
  name: "TweetDisplay",

  components: {
    TweetCard
  },

  props: {
    tweets: {
      type: Array,
      required: true
    }
  },

  data() {
    return {
      // False means list view, true means card view.
      isGridView: false
    };
  },

  methods: {
    // Switch between the two layouts.
    toggleView() {
      this.isGridView = !this.isGridView;
    }
  }
};
</script>

<style scoped>
.toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  margin-bottom: 25px;
}

.toolbar h2 {
  color: #0f172a;
}

button {
  background: #2563eb;
  color: white;
  border: none;
  padding: 12px 18px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
  transition: background 0.2s;
}

button:hover {
  background: #1d4ed8;
}

.tweet-container {
  display: grid;
  gap: 18px;
}

.list-view {
  grid-template-columns: 1fr;
}

.grid-view {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}

@media (max-width: 600px) {
  .toolbar {
    flex-direction: column;
    align-items: flex-start;
  }

  .grid-view {
    grid-template-columns: 1fr;
  }
}
</style>
