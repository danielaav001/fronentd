<template>
  <q-page class="column flex-center">
    <q-knob
      v-model="count"
      :min="min"
      :max="max"
      size="80px"
      show-value
      :thickness="0.13"
      color="primary"
      track-color="dark"
    >
      <q-avatar size="75px">
        <img icono="las la-moon" alt="" src="" />
      </q-avatar>
    </q-knob>

    <h1>bienvenido</h1>
  </q-page>
</template>
