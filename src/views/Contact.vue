<script lang="ts">
import { defineComponent, reactive, ref } from "vue";
export default defineComponent({

    setup() {
        let isValid = ref(false)
        let output = ref("")
        interface IFormInput {
            value: string,
            re: RegExp,
            error: string,
        }
        const form: Record<string, IFormInput> = reactive({
            name: {
                value: "",
                re: /^(\w{2,36}(\s\w{2,36}){0,4})?$/,
                error: "The name field it's not valid. Only alphanumeric characters are accepted",
            },
            email: {
                value: "",
                re: /^(\w+@\w+\.\w{2,10})?$/,
                error: "The email address is not valid. Please try again.",
            },
            subject: {
                value: "",
                re: /^([\w\s¡!¿?,.:;'"]{2,200})?$/,
                error: "The subject is not valid. Two characters minimum",
            },
            message: {
                value: "",
                re: /^([\w\s¡!¿?,.:;'"]{2,2000})?$/,
                error: "The message is not valid.",
            },
        })
        const validateField = (input: string, re: RegExp) => {
            const match = input.trim().match(re)
            return (match !== null) ? match[0] : null
        }

        const sendForm = () => {
            if (isValid.value) {
                output.value = `The form has been sended`
            }
        }
        const validateForm = () => {
            isValid.value = false
            let count = 0

            output.value = ""

            for (const field in form) {
                const input = form[field]

                const match = validateField(input.value, input.re)

                if (match !== null) {

                    if (!match[0]) {
                        output.value += `The ${field} field is empty. <br>`

                    } else {
                        count++
                        isValid.value = count === 4 // if the four fields are valid, then is valid the form
                    }

                } else {

                    output.value += `${input.error} <br>`
                    input.value = ""
                }

            }
            return sendForm()
        }

        return { form, validateForm, output, isValid, }
    }


})
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
    <form class="Contact" id="contactForm" autocomplete="on" method="post">
        <header class="header">
            <h2>Message me to work together!</h2>
        </header>
        <label class="label name" for="name">What's your name?<input class="input" v-model="form.name.value" name="name"
                type="text" placeholder="Text your name here"></label>

        <label class="label email" for="email">What's your email?<input class="input" name="email"
                v-model="form.email.value" type="email" placeholder="Text your email here" id="formEmail"></label>


        <input type="text" class="subject input" v-model="form.subject.value" placeholder="What it's about">
        <textarea class="input textarea" v-model="form.message.value" name="message" form="contactForm"
            placeholder="Text your message here. Thanks for contact me!"></textarea>
        <div class="submit-container">
            <button class="submit" id="submit" @click.prevent="validateForm" type="button" name="submit">Submit</button>
            <output class="output" :class="{ 'form--valid': isValid, 'form--not-valid': !isValid }" v-html="output"
                form="contactForm"></output>
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

.form--valid {
    color: green;
}

.form--not-valid {
    color: red;
}
</style>
