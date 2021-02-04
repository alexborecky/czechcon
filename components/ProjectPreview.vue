<template>
    <div class="project-preview">
        <svg width="119" height="199" viewBox="0 0 119 199" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M118.136 8.94104C92.3876 -4.17506 56.9882 -0.979698 35.2466 18.0541C21.0529 30.48 22.2392 50.0025 22.2833 69.6369M67.6363 197.427C43.5239 190.328 14.1888 186.009 3.69957 163.166C-0.328784 154.393 0.605418 145.585 3.53367 136.666" stroke="white" stroke-width="2"/>
        </svg>
        <div class="info">
            <h3>projectTitle</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Metus semper ultrices ut volutpat.</p>
            <a href="">Zobrazit projekt</a>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ProjectPreview'
    }
</script>

<style lang="scss" scoped>

.project-preview {
    max-width: 300px;
    position: relative;
    margin: 40px 0;
    svg {
        position: absolute;
        top: -40px;
        left: -56px;
    }
    .info {
        position: relative;
        p {
            margin: 16px 0
        }
        h3 {
            color: $main-orange;
        }
        a {
            float: right;
            text-transform: uppercase;
        }
    }
}

</style>