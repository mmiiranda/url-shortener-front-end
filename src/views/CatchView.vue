<template>
    <div>
        
    </div>
</template>

<script>
    export default {
        name: "CatchView",
        async beforeRouteEnter() {
            const url = new URL(window.location.href);
            
            try{
                const response = await fetch(`http://localhost:8080/api${url.pathname}`)

                const data = await response.json();
                window.location.replace(`https://${data.url}`)    
            }catch(error){
                console.error('Ocorreu um erro')
            }
        }
    }
</script>