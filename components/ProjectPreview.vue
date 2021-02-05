<template>
    <div class="project-preview">
        <svg class="element" width="119" height="199" viewBox="0 0 119 199" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M118.136 8.94104C92.3876 -4.17506 56.9882 -0.979698 35.2466 18.0541C21.0529 30.48 22.2392 50.0025 22.2833 69.6369M67.6363 197.427C43.5239 190.328 14.1888 186.009 3.69957 163.166C-0.328784 154.393 0.605418 145.585 3.53367 136.666" stroke="white" stroke-width="2"/>
        </svg>
        <div class="info flex column">
            <img :src="title" alt="">
            <p>{{description}}</p>
            <a :href="link" target="_blank" class="flex center">
                Zobrazit projekt
                <svg width="16" height="17" viewBox="0 0 16 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M6 3.96118L11 8.96118L6 13.9612" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </a>
        </div>
    </div>
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
    max-width: 300px;
    position: relative;
    margin: 40px 0;
    .element {
        position: absolute;
        top: -32px;
        left: -56px;
    }
    .info {
        position: relative;
        justify-content: flex-start;
        p {
            margin: 16px;
            align-self: flex-end;
        }
        img {
            width: auto;
            max-width: 240px;
        }
        a {
            align-self: flex-end;
            text-transform: uppercase;
            svg {
                margin-left: 2px;
                transition: .3s ease-in-out;
            }
            &:hover {
                svg {
                    transform: translateX(4px);
                    path {
                        stroke: $main-orange;
                    }
                }
            }
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

</style>