
<template>
  <div id="app">
    <header>
      <h1>TweetSpace</h1>
      <p>Share thoughts. Explore ideas.</p>
    </header>

    <main>
      <TweetDisplay :tweets="tweets" />
    </main>

    <footer>
      <p>© 2026 TweetSpace | Vue Project</p>
    </footer>
  </div>
</template>

<script>
import TweetDisplay from "./components/TweetDisplay.vue";

export default {
  name: "App",

  components: {
    TweetDisplay
  },

  data() {
    return {
      // Sample tweets stored locally.
      tweets: [
        {
          id: 1,
          user: "Alex Morgan",
          username: "alexdev",
          content: "Learning Vue.js today! Building reusable components is amazing.",
          date: "November 9, 2026"
        },
        {
          id: 2,
          user: "Sarah Lee",
          username: "sarahcodes",
          content: "Just finished my first Vue project!",
          date: "November 8, 2026"
        },
        {
          id: 3,
          user: "James Wilson",
          username: "jamesweb",
          content: "Keep learning and improving your coding skills.",
          date: "November 7, 2026"
        },
        {
          id: 4,
          user: "Mia Chen",
          username: "miadesigns",
          content: "CSS Grid and Vue make a great combination!",
          date: "November 6, 2026"
        },
        {
          id: 5,
          user: "Chris Taylor",
          username: "chrisdev",
          content: "Practice makes progress. Happy coding!",
          date: "November 5, 2026"
        },
        {
          id: 6,
          user: "Emma Rose",
          username: "emmarose",
          content: "Vue components make websites easier to maintain.",
          date: "November 4, 2026"
        }
      ]
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: "Courier New", monospace;
  background: #f1f5f9;
  color: #0f172a;
}

header {
  background: #0f172a;
  color: white;
  text-align: center;
  padding: 40px 20px;
}

header h1 {
  margin: 0;
  font-size: 36px;
}

header p {
  color: #cbd5e1;
}

main {
  max-width: 1000px;
  margin: 40px auto;
  padding: 0 20px;
  min-height: 55vh;
}

footer {
  text-align: center;
  padding: 25px;
  color: #64748b;
  font-size: 13px;
}

@media (max-width: 600px) {
  header h1 {
    font-size: 28px;
  }

  main {
    margin: 25px auto;
  }
}
</style>
