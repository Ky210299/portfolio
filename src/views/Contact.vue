<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({


});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>

    <form id="contactForm" action="" autocomplete="on" method="post"
        class="Contact">
        <label class="-label" for="formName">What's your name?</label>
        <input class="-input" type="text" id="formName">
        <label class="-label" for="formEmail">What's your email?</label>
        <input class="-input" type="email" id="formEmail">
        <label class="-label" for="formMessage"></label>
        <textarea class="-input" form="contactForm" id="formMessage"
            autocomplete="on" cols="30" rows="10" maxlength="2000"
            required></textarea>
        <output class="-output" form="contactForm"
            for="formName formEmail formMessage"></output>
        <button class="-submit" type="submit">Submit</button>
    </form>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style></style>
