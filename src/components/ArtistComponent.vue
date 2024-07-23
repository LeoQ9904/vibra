<script setup>
const props = defineProps({
  name: String,
  avatar: String
})
</script>
<template>
  <card class="overflow-hidden group" href="#">
    <div class="aspect-square">
      <img
        :src="props.avatar"
        alt="Artist Avatar"
        width="200"
        height="200"
        style="aspect-ratio: 200 / 200; object-fit: cover"
        class="rounded-t-2xl w-full h-full object-cover opacity-70 group-hover:opacity-100 transition-opacity"
      />
    </div>
    <div class="p-2 flex justify-between">
      <h3 class="text-md font-bold group-hover:text-[#4CAF50] transition-colors">
        {{ props.name }}
      </h3>
      <button
        class="border text-sm ring-offset-background rounded-full w-[100px] h-[30px] group-hover:text-[#4CAF50] group-hover:border-2 group-hover:border-[#4CAF50] transition-colors"
      >
        Ver Artista
      </button>
    </div>
  </card>
</template>
