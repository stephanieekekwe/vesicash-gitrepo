<template>
  <section id="RepoList">
    <main class="main" id="repositoryContainer">
      <div class="repository">
        <div class="repository__desc">
          <h5 class="repository__title">{{repo_clone.name}}</h5>
          <p class="repository__brief">{{repo_clone.desc}}</p>
          <div class="repository__stats">
            <div v-if="repo_clone.language" class="repository__stack">
              <div
                class="repository__stack--icon"
                v-if="repo_clone.language == 'JavaScript'"
                style="background-color:#f1e05a;"
              ></div>
              <div
                class="repository__stack--icon"
                v-else-if="repo_clone.language == 'CSS'"
                style="background-color:#563d7c;"
              ></div>
              <div
                class="repository__stack--icon"
                v-else-if="repo_clone.language == 'Jupyter Notebook'"
                style="background-color:#DA5B0B;"
              ></div>
              <div
                class="repository__stack--icon"
                v-else-if="repo_clone.language == 'HTML'"
                style="background-color:#e34c26"
              ></div>
              <div
                class="repository__stack--icon"
                v-else-if="repo_clone.language == 'Vue'"
                style="background-color: #2c3e50"
              ></div>
              <div
                class="repository__stack--icon"
                v-else-if="repo_clone.language == 'C'"
                style="background-color: #555555"
              ></div>
              <div
                class="repository__stack--icon"
                v-else-if="repo_clone.language == 'Python'"
                style="background-color: #3572A5"
              ></div>
              <div class="repository__stack--icon" v-else></div>

              <div class="repository__stack--title">{{repo_clone.language}}</div>
            </div>
            <div v-if="repo_clone.stars > 0" class="repository__star">
              <img src="../assets/svg/star-icon.svg" class="repository__star--icon" alt="star icon" />
              <span class="repository__star--count">{{repo_clone.stars}}</span>
            </div>
            <div v-if="repo_clone.forks > 0" class="repository__fork">
              <img src="../assets/svg/fork-icon.svg" alt="fork icon" class="repository__fork--icon" />
              <span class="repository__fork--count">{{repo_clone.forks}}</span>
            </div>
            <div class="repository__time-stamp">Updated on {{repo_clone.date}}</div>
          </div>
        </div>
        <button class="repository__star-action">
          <img src="../assets/svg/star-icon.svg" alt="star icon" />
          <span>Star</span>
        </button>
      </div>
    </main>
  </section>
</template>
<script>
import moment from "moment";
export default {
  name: "RepoList",
  props: {
    repo: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      repo_clone: {},
    };
  },
  mounted() {
    let date = moment(this.repo.updated_at).format("MMM D, YYYY");

    console.log(date);
    this.repo_clone = {
      name: this.repo.name,
      desc: this.repo.description,
      language: this.repo.language,
      forks: this.repo.forks,
      stars: this.repo.stargazers_count,
      date,
    };
  },
};
</script>