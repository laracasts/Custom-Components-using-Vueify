<style>
    .Alert {
        padding: 10px;
        position: absolute;
        bottom: 40px;
        right: 40px;
    }

    .Alert--Success {
        border: 10px solid green;
    }

    .Alert--Error {
        border: 10px solid red;
    }
</style>


<template>
    <div class="Alert"
         v-class="
            Alert--Success: type == 'success',
            Alert--Error: type == 'error',
         "
         v-show="show">
        <p>
            <content></content>
        </p>
    </div>

</template>

<script lang="es6">
    export default {
        props: ['type'],

        data() {
            return {
                show: true
            }
        },
        ready() {
            setTimeout(() => this.show = false, 3000);
        }
    }
</script>