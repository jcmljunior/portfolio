<template>
    <header class="container-fluid col justify-center align-center" itemscope itemtype="https://schema.org/Person">
        <h1 itemprop="name">Jcmljunior</h1>
        <h2 itemprop="jobTitle">Olá, Eu me chamo Julio <font-awesome-icon :icon="['fas', 'hand']" /></h2>
        <h3 itemprop="description">Apaixonado por tecnologia e desenvolvimento.</h3>
        <ul>
            <h4>Formas de contato</h4>
            <li itemprop="knowsAbout" v-for="(social, index) in state.social" :key="index">
                <h5 itemprop="name">{{ social.name }}</h5>
                <a itemprop="url" rel="noopener noreferrer" :href="social.link" target="_blank">
                    <font-awesome-icon :icon="social.icon" />
                </a>
            </li>
        </ul>
        <a rel="noopener noreferrer" class="button" href="https://api.whatsapp.com/send?phone=5521988156804">Entre
            em contato</a>
    </header>
    <div class="waves">
        <svg viewBox="0 0 1201 360" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
                d="M0.5 0L14.5 18C29.5 36 57.5 72 86.5 72C114.5 72 143.5 36 171.5 72C200.5 108 229.5 216 257.5 234C286.5 252 314.5 180 343.5 150C371.5 120 400.5 132 429.5 138C457.5 144 486.5 144 514.5 138C543.5 132 571.5 120 600.5 132C629.5 144 657.5 180 686.5 162C714.5 144 743.5 72 771.5 84C800.5 96 829.5 192 857.5 210C886.5 228 914.5 168 943.5 138C971.5 108 1000.5 108 1029.5 120C1057.5 132 1086.5 156 1114.5 162C1143.5 168 1171.5 156 1186.5 150L1200.5 144V360H1186.5C1171.5 360 1143.5 360 1114.5 360C1086.5 360 1057.5 360 1029.5 360C1000.5 360 971.5 360 943.5 360C914.5 360 886.5 360 857.5 360C829.5 360 800.5 360 771.5 360C743.5 360 714.5 360 686.5 360C657.5 360 629.5 360 600.5 360C571.5 360 543.5 360 514.5 360C486.5 360 457.5 360 429.5 360C400.5 360 371.5 360 343.5 360C314.5 360 286.5 360 257.5 360C229.5 360 200.5 360 171.5 360C143.5 360 114.5 360 86.5 360C57.5 360 29.5 360 14.5 360H0.5V0Z"
                fill="#0099FF" class="shape" />
        </svg>
    </div>
</template>

<script setup>
const state = {
    social: [
        {
            name: "Github",
            link: "https://github.com/jcmljunior",
            icon: ['fab', 'github']
        },
        {
            name: "E-mail",
            link: "mailto:jcmljunior@gmail.com",
            icon: ['fas', 'envelope']
        },
        {
            name: "WhatsApp",
            link: "https://api.whatsapp.com/send?phone=5521988156804",
            icon: ['fab', 'whatsapp']
        }
    ],
}
</script>

<style scoped>
header {
    min-height: calc(100vh - 25vh);
    text-align: center;
    padding: 2rem 2rem 0 2rem;

    h1 {
        font: bold italic 2rem var(--font-heading);
        margin-bottom: 1rem;
        text-shadow: 0 1px rgba(0, 0, 0, 0.3);

        &::before {
            content: "<";
        }

        &::after {
            content: "/>";
        }
    }

    h2 {
        font: bold italic 4rem var(--font-heading);
        text-shadow: 0 1px rgba(0, 0, 0, 0.3);

        .fa-hand {
            width: 4rem;
            height: 4rem;
            rotate: -22deg;
            animation: infinite 1.8s ease-in-out 0s normal none running wave;
            transform-origin: 70% 70%;
            color: var(--raised-hand);
        }
    }

    h3 {
        font: 400 italic 2.5rem var(--font-heading);
        text-shadow: 0 1px rgba(0, 0, 0, .3);
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
            border-radius: 3px;
            transition: all 0.3s ease;
            position: relative;
            text-shadow: 0 1px rgba(0, 0, 0, 0.3);
            display: flex;
            flex-direction: column;
            flex-grow: 1;
            margin: 1rem 0;

            a {
                width: 3rem;
                height: 3rem;
                line-height: 3rem;
                border-radius: 100%;
                font-size: 2rem;
                margin: 0 0.5rem;
                text-align: center;
                background-color: var(--surface-container);
                color: var(--on-surface);
                text-decoration: none;
                transition: all 0.3s ease;
                text-shadow: 0 1px rgba(0, 0, 0, 0.3);
                box-shadow: 0 2px 3px rgba(0, 0, 0, 0.3);

                &:hover {
                    background-color: var(--surface-container-highest);
                    cursor: pointer;
                }
            }

            @media (min-width: 48rem) {
                a {
                    width: 4rem;
                    height: 4rem;
                    line-height: 4rem;
                    font-size: 2.4rem;
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
        font-family: var(--font-heading);
        font-style: italic;
        font-size: 1.5rem;
        font-weight: bold;
        text-decoration: none;
        box-shadow: 0 2px 3px rgba(0, 0, 0, 0.3);
        text-shadow: 0 1px rgba(0, 0, 0, 0.3);
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

.waves {
    width: 100%;
    position: relative;
    z-index: -1;
    display: flex;
    flex-direction: column;
    justify-content: end;
    margin-bottom: -1px;
}

.waves .shape {
    fill: var(--primary-container);
}
</style>
