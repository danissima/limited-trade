<script setup>
import AppContainer from '@/components/AppContainer.vue'
import HistoryItem from '@/components/HistoryItem.vue'

const periods = [
  {
    period: '2005',
    description: 'We cooperate with dealer centres all over the country',
  },
  {
    period: '2010',
    description: 'Entering the online market',
  },
  {
    period: '2021-2023',
    description: 'Total income for the last 3 years is\u00A0$10\u00A0millons',
  },
  {
    period: '2024',
    description: 'Preparing to launch more than 10\u00A0projects in favour of vendors in different markets',
  },
]
</script>

<template>
  <section id="history" class="history section">
    <AppContainer>
      <h2 class="section__title">
        <span>History</span>
        of our development
      </h2>
      <div class="history__items">
        <HistoryItem v-for="item in periods" :key="item.period" class="history__item" :info="item" />
      </div>
    </AppContainer>
  </section>
</template>

<style lang="scss">
.history {
  padding: 120px 0;

  &__items {
    position: relative;
    display: flex;
    justify-content: space-between;

    &::before {
      content: '';
      position: absolute;
      top: 31px;
      left: 0;
      width: 100%;
      height: 1px;
      background-color: $dark-30;
      display: block;
    }
  }

  &__item {
    position: relative;
    width: 100%;
    max-width: 250px;

    &:last-child {
      background-color: $dark-100;
    }

    & + & {
      margin-left: 20px;
    }
  }

  @include break($lg) {
    padding: 80px 0;

    h2 {
      text-align: center;
    }

    &__items {
      flex-direction: column;
      align-items: center;

      &::before {
        display: none;
      }
    }

    &__item {
      max-width: 270px;

      & + & {
        margin: 30px 0 0;
      }
    }
  }
}
</style>
