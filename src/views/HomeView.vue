<template>
  <div class="h-dvh grid place-items-center">
    <div class="grid place-items-center border-4 border-black rounded p-4">
      <h1 class="text-2xl">URL SHORTENER</h1>
      <form class="flex flex-col gap-2 mt-4">
        <div><input type="text" id="" class="border-2 border-black px-1" placeholder="Url"></div>
        <input type="submit" class="bg-black text-white cursor-pointer text-md font-bold text-xl" value="Gerar">
      </form>
    </div>  
    <MessageComponent url_n="askalskalskal"/>
  </div>
</template>

<script>
import MessageComponent from '@/components/message.vue';

export default {
  name: 'HomeView',
  components: {
    MessageComponent
  }
}
</script>
