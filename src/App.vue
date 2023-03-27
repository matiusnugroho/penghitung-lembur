<template>
  <div class="flex justify-center items-center h-screen bg-gray-100">
    <div class="max-w-lg p-8 bg-white rounded shadow-lg">
      <h1 class="text-2xl font-bold mb-6">Penghitung Lemburan by Tius</h1>
      <div class="flex flex-col mb-4">
        <label for="input" class="mb-2 font-bold">Masukkan jumlah lembur:</label>
        <input
          type="number"
          id="input"
          v-model="lembur"
          class="border border-gray-300 px-3 py-2 rounded"
        >
      </div>
      <div v-if="lembur" class="text-lg font-bold mb-4">
        Gaji Anda adalah Rp {{ gaji }}
      </div>
    </div>
  </div>
</template>
<script setup>
import { computed, ref } from 'vue';

const lembur = ref(null);

const gaji = computed(() => {
  if (!lembur.value) return null;

  const result = (lembur.value * 51775) + 4901798 + 245090 - 147054;
  return result.toLocaleString();
});
</script>