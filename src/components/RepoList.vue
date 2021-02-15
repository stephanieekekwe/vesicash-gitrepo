<template>
    <section id="RepoList">
        <header class="heading">
              <div class="search">
                <div class="input__group">
                  <input type="search" class="input__field" placeholder="Find a repository...">
                </div>
              </div>
              <span class="search__desc"><b class="repoCount">15</b> results for
                <b>public</b> repositories</span>
            </header>
            <main class="main" id="repositoryContainer">
            <div class="repository">
            <div class="repository__desc">
            <h5 class="repository__title">Repo Name</h5>
            <p class="repository__brief">CSS properties that require a vendor prefix</p>
            <div class="repository__stats">
                <div class="repository__stack">
                <div class="repository__stack--icon" style="background-color:#f1e05a;"></div>
                <div class="repository__stack--title">JavaScript</div>
                </div>
                <div class="repository__star">
                <img src="../assets/svg/star-icon.svg" class="repository__star--icon" alt="star icon">
                <span class="repository__star--count">5</span>
                </div>
                <div class="repository__fork">
                <img src="../assets/svg/fork-icon.svg" alt="fork icon" class="repository__fork--icon">
                <span class="repository__fork--count">1</span>
                </div>
                <div class="repository__time-stamp">Updated on undefined 14</div>
            </div>
            </div>
            <button class="repository__star-action">
            <img src="../assets/svg/star-icon.svg" alt="star icon">
            <span>Star</span>
            </button>
        </div>
        
            </main>
    </section>
</template>
<script>
export default {
    name: 'RepoList',
    prop: {
        repos:{
            type: Array,
            required: true
        }
    },
    data(){
        return{
            
        }
    }
}
</script>