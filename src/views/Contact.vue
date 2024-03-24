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
        <header class="header">
            <h2>Message me to work together!</h2>
        </header>
        <label class="label name" for="name">What's your name?<input class="input" v-model="inputName" name="name"
                type="text" min="2" max="10" placeholder="Text your name here"></label>

        <label class="label email" for="email">What's your email?<input class="input" v-model="inputEmail" name="email"
                type="email" placeholder="Text your email here" id="formEmail"></label>


        <input type="text" class="subject input" placeholder="What it's about" v-model="subject">
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
.header {
    text-align: center;
    margin-bottom: 2rem;
    color: var(--color-palette--secondary);
    text-wrap: balance;
    font-size: 2rem;
    line-height: 150%;
}



.Contact {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: repeat(6, 3rem);
    padding-top: 4rem;
    gap: 1rem;
    border-radius: 1rem;


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
        margin: auto;
    }

    .email {
        grid-row: 2/3;
        grid-column: 1/2;
        margin: auto;
    }

    .textarea {
        margin: auto;
        width: 100%;
        height: 100%;
        max-height: 15rem;
        grid-row: 2/-3;
        grid-column: 2/3;
    }

    .subject {
        width: 100%;
        height: 100%;
        margin: auto;
        grid-row: 1/2;
        grid-column: 2/3;
        max-height: 2.5rem;
    }
}

& .submit-container {
    width: 100%;
    display: flex;
    justify-content: start;
    align-items: center;
    flex-flow: column nowrap;
    grid-row: -2/-1;
    grid-column: 1/3;
    transition: all ease-in-out .2s;

    & .submit {
        margin-bottom: 1rem;
        padding: 1rem;
        font-family: var(--font-family-secondary);
        border: 1px solid var(--color-palette--tertiary);
        background: var(--color-palette--primary);
        border-radius: .5rem;
        transition: inherit;
        color: var(--color-palette--secondary);

        &:hover {
            transform: scale(1.05);
            filter: brightness(1.1);
        }
    }

}

@media (width < 700px) {
    .Contact {

        display: flex;
        flex-flow: column nowrap;
        justify-content: center;
        align-items: flex-start;
        gap: 1rem;
        padding: 0;

        .name {
            margin: 0;
        }

        .email {
            margin: 0;

        }

        .subject {
            margin: 0;
        }

        .textarea {
            margin: 0;
        }
    }
}
</style>
