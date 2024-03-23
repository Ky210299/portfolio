<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({


});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>

    <form class="Contact" id="contactForm" action="" autocomplete="on" method="post">
        <div class="name-container">
            <label class="label" for="formName">What's your name?</label>
            <input class="input" type="text" placeholder="Text your name here" id="formName">
        </div>
        <div class="email-container">
            <label class="label" for="formEmail">What's your email?</label>
            <input class="input" type="email" placeholder="Text your email here" id="formEmail">
        </div>
        <textarea class="input" form="contactForm" id="formMessage" autocomplete="on" maxlength="2000" required
            placeholder="Text your message here. Thanks for contact me!"></textarea>
        <div class="submit-container">
            <button class="submit" type="submit">Submit</button>
            <output class="output" form="contactForm" for="formName formEmail formMessage">your message was
                correct</output>
        </div>
    </form>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
.Contact {
    width: 90vw;
    margin: auto;
    flex: 0;
    display: grid;
    grid-template-columns: 10rem 1fr;
    grid-template-rows: repeat(3, 5rem);
    gap: 2rem;


    & .label {}

    & .input {
        border: 1px solid var(--color-primary);
        padding: .3rem;
    }


    .name-container {
        grid-row: 1/2;
        grid-column: 1/2;
        margin: 1rem;
    }

    .email-container {
        grid-row: 2/3;
        grid-column: 1/2;
        margin: 1rem;
    }


    #formMessage {
        grid-row: 1/3;
        grid-column: 2/3;
        height: 100%;
        margin: 2rem;
        padding: .5rem;

    }

    & .submit-container {
        width: 100%;
        height: 6rem;
        margin: 1rem;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column nowrap;
        grid-row: 3/4;
        grid-column: 1/3;

        & .submit {
            padding: 1rem;
            margin-bottom: 1rem;

            border: 1px solid var(--color-palette--tertiary);
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
}
</style>
