<template>
  <section id="navbar">
    <!-- HEADER -->
    <header class="nav">
      <ul class="list">
        <li class="list__item">
          <a href="#" class="list__link">
            <svg
              class="nav-icons"
              height="32"
              viewBox="0 0 16 16"
              version="1.1"
              width="32"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
              />
            </svg>
          </a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">
            <div class="input__group input__group--prepend">
              <input type="search" class="input__field" placeholder="Search or jump to..." />
              <label for class="input__icon">/</label>
            </div>
          </a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">Pull requests</a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">Issues</a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">Marketplace</a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">Explore</a>
        </li>
      </ul>
      <ul class="list">
        <li class="list__item">
          <a href="#" class="list__link">
            <svg
              viewBox="0 0 16 16"
              version="1.1"
              class="nav-icons"
              width="16"
              height="16"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M8 16a2 2 0 001.985-1.75c.017-.137-.097-.25-.235-.25h-3.5c-.138 0-.252.113-.235.25A2 2 0 008 16z"
              />
              <path
                fill-rule="evenodd"
                d="M8 1.5A3.5 3.5 0 004.5 5v2.947c0 .346-.102.683-.294.97l-1.703 2.556a.018.018 0 00-.003.01l.001.006c0 .002.002.004.004.006a.017.017 0 00.006.004l.007.001h10.964l.007-.001a.016.016 0 00.006-.004.016.016 0 00.004-.006l.001-.007a.017.017 0 00-.003-.01l-1.703-2.554a1.75 1.75 0 01-.294-.97V5A3.5 3.5 0 008 1.5zM3 5a5 5 0 0110 0v2.947c0 .05.015.098.042.139l1.703 2.555A1.518 1.518 0 0113.482 13H2.518a1.518 1.518 0 01-1.263-2.36l1.703-2.554A.25.25 0 003 7.947V5z"
              />
            </svg>
          </a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">
            <svg
              viewBox="0 0 16 16"
              version="1.1"
              width="16"
              height="16"
              class="nav-icons"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M8 2a.75.75 0 01.75.75v4.5h4.5a.75.75 0 010 1.5h-4.5v4.5a.75.75 0 01-1.5 0v-4.5h-4.5a.75.75 0 010-1.5h4.5v-4.5A.75.75 0 018 2z"
              />
            </svg>
            <span>▼</span>
          </a>
        </li>
        <li class="list__item">
          <a href="#" class="list__link">
            <img v-bind:src="small_avater" alt="profile image" class="nav__img" id="nav-img" />
            <span>▼</span>
          </a>
        </li>
      </ul>
    </header>

          <header class="nav nav--sm" id="nav-sm">
        <div class="nav__header">
          <span class="burger" id="burger" @click="toggleNav()"></span>
          <a href="#" class="list__link">
            <svg
              class="nav-icons"
              height="32"
              viewBox="0 0 16 16"
              version="1.1"
              width="32"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
              />
            </svg>
          </a>
          <a href="#" class="list__link">
            <svg
              viewBox="0 0 16 16"
              version="1.1"
              class="nav-icons"
              width="16"
              height="16"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M8 16a2 2 0 001.985-1.75c.017-.137-.097-.25-.235-.25h-3.5c-.138 0-.252.113-.235.25A2 2 0 008 16z"
              />
              <path
                fill-rule="evenodd"
                d="M8 1.5A3.5 3.5 0 004.5 5v2.947c0 .346-.102.683-.294.97l-1.703 2.556a.018.018 0 00-.003.01l.001.006c0 .002.002.004.004.006a.017.017 0 00.006.004l.007.001h10.964l.007-.001a.016.016 0 00.006-.004.016.016 0 00.004-.006l.001-.007a.017.017 0 00-.003-.01l-1.703-2.554a1.75 1.75 0 01-.294-.97V5A3.5 3.5 0 008 1.5zM3 5a5 5 0 0110 0v2.947c0 .05.015.098.042.139l1.703 2.555A1.518 1.518 0 0113.482 13H2.518a1.518 1.518 0 01-1.263-2.36l1.703-2.554A.25.25 0 003 7.947V5z"
              />
            </svg>
          </a>
        </div>
        <ul class="list">
          <li class="list__item">
            <a href="#" class="list__link">
              <div class="input__group input__group--prepend">
                <input type="search" class="input__field" placeholder="Search or jump to..." />
                <label for class="input__icon">/</label>
              </div>
            </a>
          </li>
          <li class="list__item">
            <a href="#" class="list__link">Pull requests</a>
          </li>
          <li class="list__item">
            <a href="#" class="list__link">Issues</a>
          </li>
          <li class="list__item">
            <a href="#" class="list__link">Marketplace</a>
          </li>
          <li class="list__item">
            <a href="#" class="list__link">Explore</a>
          </li>
        </ul>
      </header>

  </section>
</template>
<script>
export default {
  name: "Navbar",
  props: {
    small_avater: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      show: false,
    };
  },

  methods:{

    toggleNav(){
        const burger = document.getElementById('burger')
        const nav = document.getElementById('nav-sm')

        nav.classList.toggle('open')
         // Burger toggler
        burger.classList.toggle('open')
        
    }
  },
};
</script>