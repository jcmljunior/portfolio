<template>
    <section class="skills primary-container">
        <h2>Minhas habilidades</h2>
        <p>Embora algumas tecnologias não estejam presentes adiante, isso não significa que eu não tenha tido contato
            com elas. Ao decorrer de meus estudos. Optei por destacar as que considero mais relevantes para os tipos de
            projetos que almejo desenvolver. Estou sempre disposto a aprender e explorar novas ferramentas, adaptando-me
            conforme as necessidades de cada projeto.</p>
        <div>
            <ul>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'html5']" class="icon" />
                    <h3>HTML5</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'css3']" class="icon" />
                    <h3>CSS3</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'flutter']" class="icon" />
                    <h3>Flutter</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'js']" class="icon" />
                    <h3>JavaScript</h3>
                </li>

                <li>
                    <font-awesome-icon :icon="['fab', 'vuejs']" class="icon" />
                    <h3>Vue.js</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'node']" class="icon" />
                    <h3>Node.js</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fas', 'database']" class="icon" />
                    <h3>MySQL</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fab', 'git']" class="icon" />
                    <h3>Git</h3>
                </li>
                <li>
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'linux']" class="icon" />
                    <h3>Linux</h3>
                </li>
            </ul>
        </div>
    </section>
</template>

<style scoped>
.skills {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: center;
    min-height: 100vh;
    color: var(--on-surface);
    text-align: center;
    padding: 2rem;
    flex-basis: 100%;

    h2 {
        margin-bottom: 2rem;
        font: 400 italic 3rem "Inter", serif;
    }

    >p {
        margin-bottom: 2rem;
    }

    ul {
        list-style: none;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        align-items: stretch;

        li {
            margin: 1rem;
            padding: 1rem;
            background-color: var(--inverse-primary);
            color: var(--on-surface);
            border-radius: 3px;
            transition: all 0.3s ease;
            position: relative;
            text-shadow: 0 1px rgba(0, 0, 0, .3);
            display: flex;
            flex-direction: column;
            flex-grow: 1;

            .star {
                position: absolute;
                top: -.75rem;
                right: -.75rem;
                font-size: 1.5rem;
                color: var(--star);
                text-shadow: 0 1px rgba(0, 0, 0, .3);
            }

            &:hover {
                transform: scale(1.1);
                background-color: var(--primary-fixed);
                color: var(--on-primary-fixed);
                cursor: pointer;
                z-index: 1;

                .star {
                    color: var(--inverse-star);
                }
            }

            h3 {
                margin-top: 1rem;
                font: 500 italic 1rem "Inter", serif;
                text-shadow: 0 1px rgba(0, 0, 0, .3);
            }
        }
    }

    .icon {
        font-size: 48px;
    }
}
</style>
