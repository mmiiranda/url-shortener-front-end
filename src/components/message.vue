<template>
    <div class="fixed bottom-4">
        <span id="shortener-url" class="text-2xl underline cursor-pointer">
            {{ url_n }}
        </span>
    </div>
</template>

<script>
    export default {
        name: "MessageComponent",
        data(){
            return{
                
            }
        },
        methods: {
            copyURL(){
                var copyText = document.getElementById("myInput");

                // Select the text field
                copyText.select();
                copyText.setSelectionRange(0, 99999); // For mobile devices

                // Copy the text inside the text field
                navigator.clipboard.writeText(copyText.value);
                    
                alert("Copied the text: " + copyText.value);
            }
        },
        props: {
            url_n: String,
        }       
        
    }
</script>