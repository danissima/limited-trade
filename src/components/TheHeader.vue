<script setup>
import AppContainer from '@/components/AppContainer.vue'

const navigation = [
  {
    name: 'History',
    anchor: '',
  },
  {
    name: 'Benefits',
    anchor: '',
  },
  {
    name: 'Partners',
    anchor: '',
  },
]
</script>

<template>
  <header class="header">
    <AppContainer>
      <div class="header__content">
        <div class="header__logo">
          <img src="../assets/logo.svg" alt="LDD logo">
          <span>
            Development<br>
            & distribution
          </span>
        </div>
        <nav class="header__nav">
          <ul>
            <li v-for="item in navigation" :key="item.name" class="header__link">
              <a :href="`#${item.anchor}`">{{ item.name }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </AppContainer>
  </header>
</template>

<style lang="scss">
.header {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  padding-top: 40px;
}

.header__content,
.header__logo,
.header__nav ul {
  display: flex;
  align-items: center;
}

.header__content {
  justify-content: space-between;
}

.header__logo img {
  height: 50px;
  margin-right: 20px;
}

.header__logo span {
  line-height: 19.2px;
}

.header__link {
  transition: color var(--transition);
}

.header__link:hover {
  color: var(--color-primary)
}

.header__link + .header__link {
  margin-left: 60px;
}
</style>