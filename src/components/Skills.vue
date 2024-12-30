<template>
    <section class="primary-container container-fluid">
        <h2 class="title">Minhas habilidades</h2>
        <p class="description">Embora algumas tecnologias não estejam presentes adiante, isso não significa que eu não
            tenha tido contato
            com elas. Ao decorrer de meus estudos. Optei por destacar as que considero mais relevantes para os tipos de
            projetos que almejo desenvolver. Estou sempre disposto a aprender e explorar novas ferramentas, adaptando-me
            conforme as necessidades de cada projeto.</p>
        <div>
            <ul class="row justify-center">
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'html5']" class="icon" />
                    <h3 class="title">HTML5</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'css3']" class="icon" />
                    <h3 class="title">CSS3</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'flutter']" class="icon" />
                    <h3 class="title">Flutter</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'js']" class="icon" />
                    <h3 class="title">JavaScript</h3>
                </li>

                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fab', 'vuejs']" class="icon" />
                    <h3 class="title">Vue.js</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'node']" class="icon" />
                    <h3 class="title">Node.js</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fas', 'database']" class="icon" />
                    <h3 class="title">MySQL</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fab', 'git']" class="icon" />
                    <h3 class="title">Git</h3>
                </li>
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12">
                    <font-awesome-icon :icon="['fas', 'star']" class="star" />
                    <font-awesome-icon :icon="['fab', 'linux']" class="icon" />
                    <h3 class="title">Linux</h3>
                </li>
            </ul>
        </div>
    </section>
</template>

<style scoped>
.primary-container {
    min-height: calc(100vh - 10vh);
    text-align: center;
    align-items: center;
    justify-content: center;
    padding-bottom: 2rem;
}

.primary-container>.title {
    margin-bottom: 2rem;
    font: 700 italic 3rem "Lora", serif;
    text-shadow: 0 1px rgba(0, 0, 0, .3);
}

.primary-container>.description {
    margin-bottom: 2rem;
    text-shadow: 0 1px rgba(0, 0, 0, .3);
}

.primary-container ul {
    list-style-type: none;
    gap: 1rem;
}

.primary-container li {
    border-radius: 3px;
    transition: all 0.3s ease;
    position: relative;
    text-shadow: 0 1px rgba(0, 0, 0, .3);
    background-color: var(--inverse-primary);
    color: var(--on-surface);
    text-align: center;
    padding: 1rem;
}

.primary-container li:hover {
    transform: scale(1.1);
    background-color: var(--primary-fixed);
    color: var(--on-primary-fixed);
    cursor: pointer;
    z-index: 1;
}

.primary-container li .icon {
    font-size: 3rem;
}

.primary-container li .star {
    position: absolute;
    top: -.75rem;
    right: -.75rem;
    font-size: 1.5rem;
    color: var(--star);
    text-shadow: 0 1px rgba(0, 0, 0, .3);
}

.primary-container li .title {
    margin-top: 1rem;
    text-shadow: 0 1px rgba(0, 0, 0, .3);
}

.primary-container li:hover .title {
    text-shadow: none;
}

.primary-container li:hover .star {
    color: var(--inverse-star);
}
</style>
