<script setup>
import AppContainer from '@/components/AppContainer.vue'
import BenefitsItem from '@/components/BenefitsItem.vue'
import IconCircleR from './icons/IconCircleR.vue'
import IconSquareSmile from './icons/IconSquareSmile.vue'
import IconSquaresPlus from './icons/IconSquaresPlus.vue'
import IconTopRightArrowCircleCross from './icons/IconTopRightArrowCircleCross.vue'
import IconUpDownArrowsCheckmark from './icons/IconUpDownArrowsCheckmark.vue'
import IconRocket from './icons/IconRocket.vue'

const benefits = [
  {
    icon: IconUpDownArrowsCheckmark,
    title: 'Cross-selling',
    description: 'Through well-established partnerships with leading brands and manufacturers, we can ensure our customers have access to the latest technological developments and high quality products at competitive prices',
  },
  {
    icon: IconSquaresPlus,
    title: '1 000 + SKU',
    description: 'We source electronics from leading manufacturers in Europe and Asia, offering a wide range of products including white goods, consumer electronics, mobile devices and accessories, and professional equipment',
  },
  {
    icon: IconSquareSmile,
    title: 'Service and Support',
    description: 'We place great emphasis on customer service and support, providing not only product supply but also technical support and after-sales service to ensure high levels of customer satisfaction',
  },
  {
    icon: IconTopRightArrowCircleCross,
    title: 'Organising\nturnkey expansion',
    description: 'We provide comprehensive services that cover the entire process of entering a new market, from initial analysis to full project implementation',
  },
  {
    icon: IconCircleR,
    title: 'Trademark\nregistration',
    description: 'We secure the rights to use a unique name for your products in the right jurisdiction',
  },
  {
    icon: IconRocket,
    title: 'Consulting\nand Marketing',
    description: 'We develop a market entry strategy, optimise supply chains, analyse the market and competitors, develop a marketing strategy and launch a promotion',
  },
]
</script>

<template>
  <section id="benefits" class="benefits section section_lighter">
    <AppContainer>
      <h2 class="section__title">
        <span>Benefits</span>
        and opportunities
      </h2>
      <div class="benefits__grid">
        <BenefitsItem v-for="item in benefits" :key="item.title" :info="item" />
      </div>
    </AppContainer>
  </section>
</template>

<style lang="scss">
.benefits {
  padding: 120px 0 90px;

  &__grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 80px;
  }

  @include break($lg) {
    padding: 80px 0 40px;

    &__grid {
      grid-template-columns: repeat(2, 1fr);
      gap: 40px;
    } 
  }

  @include break($md) {
    &__grid {
      grid-template-columns: 1fr;
    } 
  }
}
</style>
