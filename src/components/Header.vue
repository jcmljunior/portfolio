<template>
    <header>
        <h1>Jcmljunior</h1>
        <h2>Olá, Eu me chamo Julio <font-awesome-icon :icon="['fas', 'hand']" /></h2>
        <h3>Apaixonado por tecnologia e desenvolvimento.</h3>
        <ul>
            <h4>Formas de contato</h4>
            <li>
                <h5>Github</h5>
                <a rel="no-follow" href="https://github.com/jcmljunior" target="_blank">
                    <font-awesome-icon :icon="['fab', 'github']" />
                </a>
            </li>
            <li>
                <h5>E-mail</h5>
                <a href="mailto:jcmljunior@gmail.com">
                    <font-awesome-icon :icon="['fas', 'envelope']" />
                </a>
            </li>
        </ul>
        <a class="button" href="mailto:jcmljunior@gmail.com">Entre em contato</a>
    </header>
</template>

<style scoped>
header {
    padding: 2rem;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    text-align: center;
    padding: 1rem 2rem;

    h1 {
        font: 700 italic 2rem "Lora", serif;
        margin-bottom: 1rem;
    }

    h2 {
        font: bold italic 4rem "Lora", serif;
        text-shadow: 0 1px rgba(0, 0, 0, .3);

        .fa-hand {
            width: 4rem;
            height: 4rem;
            rotate: -22deg;
            animation-duration: 1.8s;
            animation-iteration-count: infinite;
            animation-name: wave;
            transform-origin: 70% 70%;
            color: var(--raised-hand);
        }
    }

    h3 {
        font: 400 italic 1.5rem "Inter", serif;
    }

    ul {
        list-style: none;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        align-items: stretch;

        h4,
        h5 {
            display: none;
        }

        li {
            color: var(--on-surface);
            border-radius: 3px;
            transition: all 0.3s ease;
            position: relative;
            text-shadow: 0 1px rgba(0, 0, 0, .3);
            display: flex;
            flex-direction: column;
            flex-grow: 1;
            margin: 1rem 0;

            a {
                width: 3rem;
                height: 3rem;
                line-height: 3rem;
                border-radius: 2rem;
                font-size: 1.5rem;
                margin: 0 0.5rem;
                text-align: center;
                background-color: var(--surface-container);
                color: var(--on-surface);
                text-decoration: none;
                transition: all 0.3s ease;
                text-shadow: 0 1px rgba(0, 0, 0, .3);

                &:hover {
                    background-color: var(--surface-container-highest);
                    cursor: pointer;
                }
            }
        }
    }

    .button {
        display: flex;
        padding: 1rem 2rem;
        border-radius: 3px;
        font-size: 2rem;
        transition: all 0.3s ease;
        font: bold italic 1.5rem "Inter", serif;
        text-decoration: none;
        text-shadow: 0 1px rgba(0, 0, 0, .3);
        background-color: var(--inverse-primary);
        color: var(--on-surface);
        margin-top: 2.5rem;

        &:hover {
            background-color: var(--primary-fixed);
            color: var(--on-primary-fixed);
            cursor: pointer;
        }
    }
}
</style>
