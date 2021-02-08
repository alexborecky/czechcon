<template>
    <a :href="link" target="_blank" class="project-preview flex">
        <svg class="element" width="119" height="229" viewBox="0 0 119 199" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M118.136 8.94104C92.3876 -4.17506 56.9882 -0.979698 35.2466 18.0541C21.0529 30.48 22.2392 50.0025 22.2833 69.6369M67.6363 197.427C43.5239 190.328 14.1888 186.009 3.69957 163.166C-0.328784 154.393 0.605418 145.585 3.53367 136.666" stroke="white" stroke-width="2"/>
        </svg>
        <div class="info flex column">
            <img :src="title" alt="">
            <p>{{description}}</p>
            <!-- <a :href="link" target="_blank" class="flex center">
                Zobrazit projekt
                <svg width="16" height="17" viewBox="0 0 16 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M6 3.96118L11 8.96118L6 13.9612" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </a> -->
        </div>
    </a>
</template>

<script>
    export default {
        name: 'ProjectPreview',
        props: [
            'title',
            'description',
            'link'
        ]
    }
</script>

<style lang="scss" scoped>

.project-preview {
    max-width: 30%;
    flex-grow: 1;
    position: relative;
    margin: 40px 0;
    align-items: flex-start;
    .element {
        position: absolute;
        top: -40px;
        left: -56px;
    }
    .info {
        position: relative;
        justify-content: flex-start;
        width: 100%;
        p {
            margin: 16px;
            // align-self: flex-end;
            font-weight: normal;
            opacity: .8;
            transition: .3s ease-in-out;
        }
        img {
            width: auto;
            max-width: 240px;
        }
    }
    svg {
        transition: .3s ease-in-out;
        path {
            transition: .3s ease-in-out;
        }
    }
    &:hover {
        svg {
            transform: rotate(-20deg) translateY(8px);
            path {
                stroke: $main-orange;
            }
        }
        p {
            transform: translateX(8px);
            opacity: 1;
        }
    }
    @media only screen and (max-width: 1500px) {
        max-width: 400px;
    }
    @media only screen and (max-width: 1280px) {
        max-width: 300px;
    }
    @media only screen and (max-width: 960px) {
        max-width: 400px;
        margin-bottom: 80px;
        .element {
            left: -40px;
            top: -24px;
        }
    }
    @media only screen and (max-width: 550px) {
        max-width: 80%;
        .element {
            left: -40px;
            top: -24px;
        }
    }
}

.ready {
    opacity: 0.4;
    .info {
        img {
            max-width: 140px;
        }
    }
}

</style>