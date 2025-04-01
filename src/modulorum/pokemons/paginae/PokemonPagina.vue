<template>
  <section class="flex flex-col">
    <h1 class="text-3xl font-bold">
      Pokèmon <small class="text-blue-500">#{{ id }}</small>
    </h1>
    <img
      :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${id}.svg`"
      alt="Pokèmon"
      class="w-[200px] h-[200px]"
      width="200"
      height="200"
    />

    <RouterLink
      :to="{ name: 'pokemon', params: { id: Number(id) + 1 } }"
      class="bg-blue-500 text-white p-2 mt-5 rounded-md text-center hover:bg-blue-700"
    >
      Siguiente
    </RouterLink>
    <RouterLink
      :to="{ name: 'pokemon', params: { id: Math.max(1, Number(id) - 1) } }"
      class="bg-blue-500 text-white p-2 mt-5 rounded-md text-center hover:bg-blue-700"
    >
      Anterior
    </RouterLink>
  </section>
</template>

<script lang="ts" setup>
interface Props {
  id: string;
}

const props = defineProps<Props>();

</script>
