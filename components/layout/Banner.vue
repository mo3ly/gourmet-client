<template>
  <section class="text-gray-600 bg-pink-300 bg-opacity-5 dark:bg-opacity-5 dark:bg-gray-200  border-b-2 dark:border-gray-500 dark:border-opacity-20 pattern-bg-typo">
    <div class="container py-0 mx-auto">
      <div class="flex items-center justify-center w-full space-x-3 pt-5 text-xs">
        <NuxtLink :to="localePath('/')" class=" px-3 bg-pink-200 text-pink-800 rounded-full">{{ $t("header.links[0].name") }}</NuxtLink>
        <slot name="breadcrumb"></slot>
      </div>
      <div class="container items-center px-5 _pt-8 py-5 lg:px-20 animate__animated animate__rollIn">
        <div class="flex flex-wrap">
          <div class="w-full mx-auto mt-1 mb-4 bg-white dark:bg-dark-surface dark:border-dark-border border rounded-lg shadow-xl lg:w-1/2">
            <div class="p-6 text-center">
              <slot name="content"></slot>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
