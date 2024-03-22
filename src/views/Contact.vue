<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({


});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>

    <form class="Contact" id="contactForm" action="" autocomplete="on" method="post">
        <label class="label" for="formName">What's your name?</label>
        <input class="input" type="text" id="formName">
        <label class="label" for="formEmail">What's your email?</label>
        <input class="input" type="email" id="formEmail">
        <label class="label" for="formMessage"></label>
        <textarea class="input" form="contactForm" id="formMessage" autocomplete="on" cols="30" rows="10"
            maxlength="2000" required placeholder="Text your message here. Thanks for contact me!"></textarea>
        <div class="submit-container">
            <button class="submit" type="submit">Submit</button>
            <output class="output" form="contactForm" for="formName formEmail formMessage">your message was
                correct</output>
        </div>
    </form>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
* {
    outline: 1px solid white;
}


.Contact {
    width: 90vw;
    margin: auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;


    & .label {
        border: 2px solid white;
    }

    & .submit-container {

        width: 100%;
        height: 6rem;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column nowrap;

        & .submit {
            padding: 1rem;
            margin-bottom: 1rem;
            border: 2px solid var(--color-palette--secondary);
            background: var(--color-palette--primary);
            border-radius: .5rem;
            transition: all ease-in-out .2s;

            &:hover {
                transform: scale(1.05);
            }
        }

        & .output {
            /* visibility: hidden; */
            padding-inline: 1rem;
        }
    }

    .formName {
        grid-row: 1;
        grid-column: 1;
    }

    .formEmail {
        grid-row: 2;
        grid-column: 1;
    }

    .submit-container {
        grid-row: 3;
        grid-column: 1;
    }

    .formMessage {
        grid-row: 1/3;
        grid-column: 2;

    }
}
</style>
