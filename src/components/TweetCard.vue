
<template>
  <article class="tweet-card">
    <div class="tweet-header">
      <div class="avatar">
        {{ tweet.user.charAt(0) }}
      </div>

      <div class="user-info">
        <h3>{{ tweet.user }}</h3>
        <span>@{{ tweet.username }}</span>
      </div>
    </div>

    <p class="tweet-content">{{ tweet.content }}</p>

    <div class="tweet-footer">
      <span>{{ tweet.date }}</span>
      <span>💬 Tweet</span>
    </div>
  </article>
</template>

<script>
export default {
  name: "TweetCard",

  props: {
    tweet: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
.tweet-card {
  background: white;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  padding: 20px;
  transition: 0.2s ease;
  height: 100%;
  box-sizing: border-box;
}

.tweet-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08);
}

.tweet-header {
  display: flex;
  align-items: center;
  gap: 12px;
}

.avatar {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: #2563eb;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  flex-shrink: 0;
}

.user-info h3 {
  margin: 0;
  font-size: 16px;
}

.user-info span {
  color: #64748b;
  font-size: 13px;
}

.tweet-content {
  line-height: 1.6;
  color: #334155;
  margin: 18px 0;
}

.tweet-footer {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  color: #94a3b8;
  font-size: 12px;
}
</style>
