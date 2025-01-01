<template>
    <div class="waves">
        <svg viewBox="0 0 1200 308" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
                d="M0 252L9 222C18 192 36 132 55 126C73 120 91 168 109 174C127 180 145 144 164 144C182 144 200 180 218 204C236 228 255 240 273 216C291 192 309 132 327 150C345 168 364 264 382 252C400 240 418 120 436 84C455 48 473 96 491 114C509 132 527 120 545 132C564 144 582 180 600 210C618 240 636 264 655 252C673 240 691 192 709 180C727 168 745 192 764 198C782 204 800 192 818 168C836 144 855 108 873 126C891 144 909 216 927 258C945 300 964 312 982 306C1000 300 1018 276 1036 264C1055 252 1073 252 1091 246C1109 240 1127 228 1145 222C1164 216 1182 216 1191 216H1200V0H1191C1182 0 1164 0 1145 0C1127 0 1109 0 1091 0C1073 0 1055 0 1036 0C1018 0 1000 0 982 0C964 0 945 0 927 0C909 0 891 0 873 0C855 0 836 0 818 0C800 0 782 0 764 0C745 0 727 0 709 0C691 0 673 0 655 0C636 0 618 0 600 0C582 0 564 0 545 0C527 0 509 0 491 0C473 0 455 0 436 0C418 0 400 0 382 0C364 0 345 0 327 0C309 0 291 0 273 0C255 0 236 0 218 0C200 0 182 0 164 0C145 0 127 0 109 0C91 0 73 0 55 0C36 0 18 0 9 0H0V252Z"
                fill="#0099FF" class="shape" />
        </svg>
    </div>
    <footer class="container-fluid col justify-center align-center">
        <p>© 2024 - 2025, jcmljunior todos os direitos reservados.</p>
        <p>Desenvolvido por <a href="https://github.com/jcmljunior" target="_blank">Julio Cesar</a>
        </p>
    </footer>
</template>

<style scoped>
footer {
    min-height: 10vh;
    text-align: center;
    padding: 2rem;
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
