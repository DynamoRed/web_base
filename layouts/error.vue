<template>
    <div class="error-page">
        <h1>Erreur {{error.statusCode}}</h1>
        <span v-if="error.statusCode === 404">Whoops ! Page not found...</span>
        <span v-else>Hmmm that's embarrassing...<br>An error has occured !</span>
        <NuxtLink to="/" class="btn-primary btn-main btn-back">Return to a safe place</NuxtLink>
    </div>
</template>

<script>
    export default {
        props: ['error'],
        data(){
            return {
                pageTitle: `Une erreur est survenue !`,
            }
        },
        head() {
            return {
                title: this.pageTitle,
            }
        },
    }
</script>

<style lang="css" scoped>
    .error-page {
        background: linear-gradient(315deg, #0B090A, #161A1D), #0B090A;
        background-blend-mode: soft-light, normal;
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .error-page h1 {
        color: var(--secondary-clr);
        text-transform: uppercase;
        letter-spacing: 0.04em;
        font-weight: 800;
        font-size: 72px;
        line-height: 86px;
        background:linear-gradient(315deg, var(--primary-clr) 0%, var(--secondary-clr) 100%);
        background-clip: text;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
    }

    .error-page span {
        font-size: 32px;
        line-height: 40px;
        margin: 8px;
        text-align: center;
    }

    .error-page .btn-back {
        text-transform: none;
        font-weight: 500;
        font-size: 20px;
        line-height: 24px;
        letter-spacing: 4%;
        padding: 8px 24px;
        letter-spacing: 0.04em;
        color: var(--primary-clr);
        position: absolute;
        bottom: 26px;
        left: 26px;
    }
</style>