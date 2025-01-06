<template>
    <section class="primary-container container-fluid" itemscope itemtype="https://schema.org/DefinedTermSet">
        <h2 class="title" itemprop="name">Minhas habilidades</h2>
        <p class="description">Embora algumas tecnologias não estejam presentes adiante, isso não significa que eu não
            tenha tido contato
            com elas. Ao decorrer de meus estudos. Optei por destacar as que considero mais relevantes para os tipos de
            projetos que almejo desenvolver. Estou sempre disposto a aprender e explorar novas ferramentas, adaptando-me
            conforme as necessidades de cada projeto.</p>
        <div>
            <ul class="row justify-center">
                <li class="col-lg-2 col-md-3 col-sm-3 col-xs-12" itemscope itemtype="https://schema.org/DefinedTerm"
                    v-for="(skill, index) in state.items" :key="index">
                    <font-awesome-icon :icon="[skill.icon.split(' ')[0], skill.icon.split(' ')[1]]" class="icon" />
                    <h3 class="title" itemprop="name">{{ skill.title }}</h3>
                </li>
            </ul>
        </div>
    </section>
</template>

<script setup>
const state = {
    items: [
        {
            icon: "fab fa-html5",
            title: "HTML5"
        },
        {
            icon: "fab fa-css3",
            title: "CSS3"
        },
        {
            icon: "fab fa-flutter",
            title: "Flutter"
        },
        {
            icon: "fab fa-js",
            title: "JavaScript"
        },
        {
            icon: "fab fa-vuejs",
            title: "Vue.js"
        },
        {
            icon: "fab fa-node",
            title: "Node.js"
        },

        {
            icon: "fas fa-database",
            title: "Banco de Dados"
        }, {
            icon: "fab fa-git",
            title: "Git"
        },
        {
            icon: "fab fa-linux",
            title: "Linux"
        },
    ],
}
</script>

<style scoped>
.primary-container {
    text-align: center;
    align-items: center;
    justify-content: center;
    padding-bottom: 2rem;
}

.primary-container>.title {
    margin-bottom: 2rem;
    font: bold italic 3rem var(--font-heading);
    text-shadow: 0 1px rgba(0, 0, 0, 0.3);
}

.primary-container>.description {
    margin-bottom: 2rem;
    text-shadow: 0 1px rgba(0, 0, 0, 0.3);
}

.primary-container ul {
    list-style-type: none;
    gap: 1rem;
}

.primary-container li {
    border-radius: 3px;
    transition: all 0.3s ease;
    position: relative;
    text-shadow: 0 1px rgba(0, 0, 0, 0.3);
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

.primary-container li .title {
    margin-top: 1rem;
    text-shadow: 0 1px rgba(0, 0, 0, 0.3);
}
</style>
