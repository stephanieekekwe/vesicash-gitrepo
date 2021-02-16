<template>
  <section id="app">
    <div class="main-content" id="mainContent">
      <Navbar :small_avater="small_avater" />


      <div class="profile profile--sm" id="profile-sm">
        <div v-if="user_details" class="profile__header">
          <div class="profile__img-container">
            <img v-bind:src="user_details.avatar_url" alt="profile image" class="profile__img" />
          </div>
          <div class="profile__names">
            <h4 class="profile__name">{{user_details.name}}</h4>
            <h5 class="profile__user-name">{{user_details.login}}</h5>
          </div>
        </div>
        <p class="profile__desc">{{user_details.bio}}</p>
        <button class="follow__btn">Follow</button>
        <div class="followers__counts">
          <p>
            <span class="text-bold">
              <svg
                class="octicon octicon-people text-gray-light"
                height="12"
                viewBox="0 0 16 16"
                version="1.1"
                width="17"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M5.5 3.5a2 2 0 100 4 2 2 0 000-4zM2 5.5a3.5 3.5 0 115.898 2.549 5.507 5.507 0 013.034 4.084.75.75 0 11-1.482.235 4.001 4.001 0 00-7.9 0 .75.75 0 01-1.482-.236A5.507 5.507 0 013.102 8.05 3.49 3.49 0 012 5.5zM11 4a.75.75 0 100 1.5 1.5 1.5 0 01.666 2.844.75.75 0 00-.416.672v.352a.75.75 0 00.574.73c1.2.289 2.162 1.2 2.522 2.372a.75.75 0 101.434-.44 5.01 5.01 0 00-2.56-3.012A3 3 0 0011 4z"
                />
              </svg>
              {{user_details.followers}}
            </span> followers .
            <span class="text-bold">{{user_details.following}}</span> following.
            <span class="text-bold">
              <svg
                class="octicon octicon-star text-gray-light"
                height="12"
                viewBox="0 0 16 16"
                version="1.1"
                width="16"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"
                />
              </svg> 3
            </span>
          </p>
        </div>

        <div class="other__bio">
          <p>
            <svg
              class="octicon octicon-location"
              viewBox="0 0 16 16"
              version="1.1"
              width="12"
              height="16"
              aria-hidden="true"
            >
              <path
                fill-rule="evenodd"
                d="M11.536 3.464a5 5 0 010 7.072L8 14.07l-3.536-3.535a5 5 0 117.072-7.072v.001zm1.06 8.132a6.5 6.5 0 10-9.192 0l3.535 3.536a1.5 1.5 0 002.122 0l3.535-3.536zM8 9a2 2 0 100-4 2 2 0 000 4z"
              />
            </svg>
            {{user_details.location}}
          </p>
        </div>
      </div>
      <!-- nav-2 -->
      <div v-if="repos" class="sticky__container">
        <div class="container">
          <nav class="nav-2 u-grid-25-75">
            <div class="col-1"></div>
            <div class="col-2">
              <ul class="list">
                <li class="list__item">
                  <a href="#" class="list__link">
                    <img src="./assets/svg/overview-icon.svg" alt="overview-icon" />
                    <p class="list__title">Overview</p>
                  </a>
                </li>
                <li class="list__item active">
                  <a href="#" class="list__link">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="nav-icon-2"
                      height="16"
                      viewBox="0 0 16 16"
                      version="1.1"
                      width="16"
                      aria-hidden="true"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"
                      />
                    </svg>
                    <p class="list__title">Repositories</p>
                    <div class="list__count repoCount">{{repos.length}}</div>
                  </a>
                </li>
                <li class="list__item">
                  <a href="#" class="list__link">
                    <img src="./assets/svg/projects-icon.svg" alt="projects icon" />
                    <p class="list__title">Projects</p>
                  </a>
                </li>
                <li class="list__item">
                  <a href="#" class="list__link">
                    <img src="./assets/svg/package-icon.svg" alt="packages icon" />
                    <p class="list__title">Packages</p>
                  </a>
                </li>
              </ul>
            </div>
          </nav>
        </div>
      </div>

      <div class="container">
        <div class="u-grid-25-75">
          <div class="col-1">
            <div v-if="user_details" class="profile" id="profile-lg">
              <div class="profile__img-container">
                <img v-bind:src="user_details.avatar_url" alt="profile image" class="profile__img" />
              </div>
              <h4 class="profile__name">{{user_details.name}}</h4>
              <h5 class="profile__user-name">{{user_details.login}}</h5>
              <p class="profile__desc">{{user_details.bio}}</p>
              <button class="follow__btn">Follow</button>
              <div class="followers__counts">
                <p>
                  <svg
                    class="octicon octicon-people text-gray-light"
                    height="12"
                    viewBox="0 0 16 16"
                    version="1.1"
                    width="17"
                    aria-hidden="true"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M5.5 3.5a2 2 0 100 4 2 2 0 000-4zM2 5.5a3.5 3.5 0 115.898 2.549 5.507 5.507 0 013.034 4.084.75.75 0 11-1.482.235 4.001 4.001 0 00-7.9 0 .75.75 0 01-1.482-.236A5.507 5.507 0 013.102 8.05 3.49 3.49 0 012 5.5zM11 4a.75.75 0 100 1.5 1.5 1.5 0 01.666 2.844.75.75 0 00-.416.672v.352a.75.75 0 00.574.73c1.2.289 2.162 1.2 2.522 2.372a.75.75 0 101.434-.44 5.01 5.01 0 00-2.56-3.012A3 3 0 0011 4z"
                    />
                  </svg>
                  <span class="text-bold">{{user_details.followers}}</span> followers .
                  <span class="text-bold">{{user_details.following}}</span> following.
                  <svg
                    class="octicon octicon-star text-gray-light"
                    height="11"
                    viewBox="0 0 16 16"
                    version="1.1"
                    width="15"
                    aria-hidden="true"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"
                    />
                  </svg>
                  <span class="text-bold">3</span>
                </p>
              </div>

              <div class="other__bio">
                <p>
                  <svg
                    class="octicon octicon-location"
                    viewBox="0 0 16 16"
                    version="1.1"
                    width="13"
                    height="16"
                    aria-hidden="true"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M11.536 3.464a5 5 0 010 7.072L8 14.07l-3.536-3.535a5 5 0 117.072-7.072v.001zm1.06 8.132a6.5 6.5 0 10-9.192 0l3.535 3.536a1.5 1.5 0 002.122 0l3.535-3.536zM8 9a2 2 0 100-4 2 2 0 000 4z"
                    />
                  </svg>
                  {{user_details.location}}
                </p>
              </div>
            </div>
          </div>
          <div class="col-2">
            <header class="heading">
              <div class="search">
                <div class="input__group">
                  <input type="search" class="input__field" placeholder="Find a repository..." />
                </div>
              </div>
              <span class="search__desc">
                <b class="repoCount">{{repos.length}}</b> results for
                <b>public</b> repositories
              </span>
            </header>
            <div></div>
            <RepoList :key="repo.id" v-for="repo in repos" :repo="repo" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import Navbar from "./components/Navbar";
import RepoList from "./components/RepoList";

export default {
  name: "App",
  components: {
    Navbar,
    RepoList,
  },
  data() {
    return {
      repos: [],
      user_details: [],
      small_avater: "",
      num_of_repos: ""
    };
  },
  
  created() {
    let user_details_url = "https://api.github.com/users/stephanieekekwe";
    let repo_url = "https://api.github.com/users/stephanieekekwe/repos";
    axios.get(repo_url).then((response) => {
      this.repos = response.data;
      console.log(this.repos);
    });

    axios.get(user_details_url).then((response) => {
      this.user_details = response.data;
      this.small_avater = this.user_details.avatar_url;
      console.log(this.user_details);
    });
  },
};
</script>

<style>
@import "./App.css";
</style>
