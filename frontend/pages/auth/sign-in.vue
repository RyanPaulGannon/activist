<template>
  <div class="px-4 2xl:px-36 xl:px-24 md:px-8 sm:px-6">
    <form class="space-y-4">
      <div class="col">
        <FormTextField
          @update:model-value="userNameValue = $event"
          :placeholder="$t('pages.auth.sign-in.index.enter-user-name')"
          :model-value="userNameValue"
        />
      </div>
      <div>
        <FormTextField
          @update:model-value="passwordValue = $event"
          :placeholder="$t('pages.auth.sign-in.index.enter-password')"
          :is-icon-visible="true"
          input-type="password"
          :model-value="passwordValue"
          :icons="['bi:eye-fill']"
        />
      </div>
      <div class="flex space-x-2">
        <button
          class="flex items-center w-fit justify-center 2xl:space-x-10 xl:space-x-8 lg:space-x-4 md:space-x-4 lg:col-span-5 md:col-span-2 px-3 rounded border light:border-black dark:border-[#857E7B] text-sm h-[48px] md:h-[40px]"
          type="button"
          aria-label="test"
        >
          <span class="flex items-center space-x-4 whitespace-nowrap">
            <Icon name="bi:shield-fill-check" size="28px" />
            <span class="font-bold text-[18px] hidden lg:inline-block">{{
              $t("pages.auth.sign-in.index.i-am-human")
            }}</span>
          </span>
          <span class="text-[12px] hidden lg:inline-block truncate"
            >FriendlyCaptcha</span
          >
        </button>
        <BtnLabeled
          @click="signIn"
          class="flex items-center justify-center truncate max-h-[48px] md:max-h-[40px] w-[116px] md:w-[96px]"
          :label="$t('components.btn-labeled.sign-in')"
          :cta="true"
          fontSize="lg"
          :ariaLabel="$t('components.btn-labeled.sign-in-aria-label')"
        />
      </div>
      <div class="flex pt-4 md:justify-center md:pt-6 lg:pt-8">
        <h6>{{ $t("pages.auth.sign-in.index.no-account") }}</h6>
        <NuxtLink :to="'sign-up'" class="ml-2 font-extrabold link-text">{{
          $t("pages.auth.sign-in.index.sign-up")
        }}</NuxtLink>
      </div>
    </form>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: "auth",
});

const userNameValue = ref("");
const passwordValue = ref("");

const signIn = () => {
  //
};
</script>
