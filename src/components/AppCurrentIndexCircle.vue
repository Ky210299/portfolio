<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({

})


</script>
 
 ««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
    <svg width="20" height="20">
        <defs>
            <radialGradient id="myGradient">
                <stop offset="60%" stop-color="blue" />
                <stop offset="80%" stop-color="#0077ff" />
                <stop offset="100%" stop-color="white" />
            </radialGradient>
        </defs>
        <circle cx="10" cy="10" class="enabled svg__index-circle" />
    </svg>
</template>

 
 ««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
    

.enabled {
    r: 10;
    fill: url('#myGradient');
    


}

.disabled {
    fill: gray;
    fill-opacity: .6;
    r: 5;

    &:active {
        fill: rgb(159, 167, 191);
        r: 7;
        fill-opacity: 1;
    }
}
</style>