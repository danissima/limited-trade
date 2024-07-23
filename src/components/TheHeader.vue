<script setup>
import AppContainer from '@/components/AppContainer.vue'
import AppButton from '@/components/AppButton.vue'

const navigation = [
  {
    name: 'History',
    anchor: 'history',
  },
  {
    name: 'Benefits',
    anchor: 'benefits',
  },
  {
    name: 'Partners',
    anchor: 'partners',
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
        <AppButton class="header__contact" size="small" kind="outline" is-link href="#contact">
          Contact
        </AppButton>
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

  &__content,
  &__logo,
  &__nav ul {
    display: flex;
    align-items: center;
  }

  &__content {
    justify-content: space-between;
  }

  &__logo {
    img {
      height: 50px;
      margin-right: 20px;
    }

    span {
      line-height: 19.2px;
    }
  }

  &__link {
    transition: color $transition;
    font-size: 14px;
    line-height: 16.44px;

    &:hover {
      color: $primary;
    }

    & + & {
      margin-left: 60px;
    }
  }

  @include break($lg) {
    &__logo {
      img {
        height: 24px;
      }

      span {
        display: none;
      }
    }

    &__link {
      & + & {
        margin-left: 20px;
      }
    }

    &__contact {
      display: none;
    }
  }
}
</style>