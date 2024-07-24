<script setup>
import AppContainer from '@/components/AppContainer.vue'
import AppInput from '@/components/AppInput.vue'
import AppButton from '@/components/AppButton.vue'
import AppCheckbox from '@/components/AppCheckbox.vue'
</script>

<template>
  <section id="contact" class="contact section">
    <AppContainer>
      <div class="contact__content">
        <div class="contact__title">
          <h2 class="section__title">
            We will send you <span>commercial&nbsp;offer</span>
          </h2>
          <p>We will help you organise the whole supply chain from the manufacturer to the shelf in the shop</p>
        </div>
        <form class="contact__form">
          <AppInput placeholder="Name" />
          <AppInput type="email" placeholder="E-mail" />
          <AppInput type="tel" placeholder="Phone number" />
          <AppCheckbox
            id="contact-agreement"
            name="agreement"
            checked
          >
            I agree with the privacy policy of the site
          </AppCheckbox>
          <AppButton kind="primary">Get a commercial offer</AppButton>
        </form>
      </div>
    </AppContainer>
  </section>
</template>

<style lang="scss">
.contact {
  padding: 140px 0;

  &__content {
    display: flex;
    justify-content: space-between;
  }

  &__title {
    margin-right: 40px;
    width: 100%;
    max-width: 460px;

    h2 {
      margin-bottom: 40px;
      font-size: 60px;
      line-height: 70.44px;
    }

    p {
      font-size: 20px;
      line-height: 23.48px;
    }
  }

  &__form {
    width: 100%;
    max-width: 520px;

    .input {
      margin-bottom: 20px;
    }

    .button {
      margin-top: 30px;
    }
  }

  @include break($lg) {
    padding: 80px 0;

    &__content {
      flex-direction: column;
    }

    &__title {
      margin: 0 0 30px;
      max-width: none;

      h2 {
        margin-bottom: 20px;
        font-size: 24px;
        line-height: 28.18px;
      }

      p {
        font-size: 14px;
        line-height: 19.6px;
      }
    }

    &__form {
      max-width: none;

      .button {
        width: 100%;
      }
    }
  }
}
</style>
