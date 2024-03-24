<script lang="ts">
import { defineComponent, ref } from "vue";
export default defineComponent({
    setup() {
        let inputName = ref("")
        let inputEmail = ref("")
        let inputMessage = ref("")
        let subject = ref("")
        let output = ref("")



        return { inputName, inputEmail, inputMessage, subject, output }
    }
});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>

    <form class="Contact" id="contactForm" autocomplete="on" method="post">
        <label class="label name" for="name">What's your name?<input class="input" v-model="inputName" name="name"
                type="text" min="2" max="10" placeholder="Text your name here"></label>

        <label class="label email" for="email">What's your email?<input class="input" v-model="inputEmail" name="email"
                type="email" placeholder="Text your email here" id="formEmail"></label>


        <input type="text" class="subject input" placeholder="Subject" v-model="subject">
        <textarea class="input textarea" v-model="inputMessage" name="message" form="contactForm" autocomplete="on"
            maxlength="2000" placeholder="Text your message here. Thanks for contact me!"></textarea>
        <div class="submit-container">
            <button class="submit" name="submit" type="submit">Submit</button>
            <output class="output" form="contactForm" for="name email message">{{ output }}</output>
        </div>
    </form>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style scoped>
.Contact {
    width: 90vw;
    margin: auto;
    display: grid;
    grid-template-columns: 10rem 1fr;
    grid-template-rows: repeat(7, 1fr);
    column-gap: 3rem;

    & .label {
        line-height: 100%;
        margin-bottom: 1rem;
    }

    & .input {
        outline: 1px solid var(--color-primary);
        padding: .5rem;
        margin-top: .2rem;
    }



    .name {
        grid-row: 1/2;
        grid-column: 1/2;
    }

    .email {
        grid-row: 2/3;
        grid-column: 1/2;
    }

    .textarea {
        height: 100%;
        grid-row: 2/-3;
        grid-column: 2/3;
    }

    .subject {
        grid-row: 1/2;
        grid-column: 2/3;
    }
}

& .submit-container {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: column nowrap;
    grid-row: -2/-1;
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
</style>
