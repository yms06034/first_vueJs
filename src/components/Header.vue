<template>
  <header>
    <div
      id="top-navbar--wrap"
      class="top-navbar">
      <div>
        <!-- <a
          class="aa pad-15 weight primary"
          href="/">HOME</a> -->
      </div>
      <div class="navber_right">
        <div 
          v-for="nav in navigations"
          :key="nav.name">
          <RouterLink 
            :to="nav.href"
            active-class="a_active"
            class="pad-15">
            {{ nav.name }}
          </RouterLink>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navigations : [
        {
          name: '사업안내',
          href: '',
        },
        {
          name: '단지안내',
          href: ''
        },
        {
          name: '상품안내',
          href: ''
        },
        {
          name: '분양일정',
          href: ''
        },
        {
          name: '계약안내',
          href: ''
        },
        {
          name: '청약안내',
          href: ''
        },
        {
          name: '프리미엄',
          href: ''
        }
      ],
    };
  },
}
</script>

<script setup>
import { loadFull } from "tsparticles";
const particlesInit = async engine => {
    await loadFull(engine);
};
const particlesLoaded = async container => {
    console.log("Particles container loaded", container);
};

console.log(particlesInit);
console.log(particlesLoaded);
</script>

<style lang="scss" scope>
$primary1: #001140;
$primary2: #273D6B;
$primary3: #C9DBED;

.pad-15 {
  padding: 15px 15px 10px 15px;
}

header { 
  .top-navbar {
    margin: 0 auto;
    max-width: 1140px;
    padding-top: 35px;
    padding-bottom: 30px;
    display: flex;
    justify-content: center;
    .aa {
      font-size: 18px;
    &:hover {
        color: #251667; 
    }
      }
    .navber_right {
      display: flex;
      flex-direction: row;
      font-family: 'Montserrat', 'Helvetica Neue', Helvetica, Arial, sans-serif;
      a {
        &:hover {
          color: $primary1;
          border-bottom: 3px solid #001140;
        }
      }
    }
  }
}
</style>
  