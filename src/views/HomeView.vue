<template>
  <div class="h-dvh grid place-items-center">
    <div class="grid place-items-center border-2 border-black rounded p-4 box shadow-md">
      <h1 class="text-2xl">URL SHORTENER</h1>
      <form class="flex flex-col gap-2 mt-4" @submit="submitForm()">
        <div><input type="text" v-model="inputURL" class="border-2 border-black px-1" placeholder="Url"></div>
        <input type="submit" class="bg-black text-white cursor-pointer text-md font-bold text-xl" value="Gerar">
      </form>
    </div>  
    <div class="fixed bottom-4">
      <span id="shortener-url" @click="copyURL()" class="text-2xl underline cursor-pointer">
        {{ novaURL }}
      </span>
  </div>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  data(){
    return {
      inputURL: '',
      novaURL: ''
    }
  },  
  methods: {
    submitForm(){
        try{
          event.preventDefault()
          let url = this.inputURL.trim(" ")
          if(url != ''){
              const isCorrect = new URL(url);
              console.log(isCorrect)
              this.novaURL = isCorrect.pathname
          }else{
            alert('insira uma url')
          }
        }catch (err){
          alert("URL inválida")
        }
    },
    copyURL(){
      navigator.clipboard.writeText(this.novaURL);
      alert("url copiada")
    }
  }
}
</script>
