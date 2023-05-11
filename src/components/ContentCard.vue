<template>
<div class="card shadow">
    <div v-if="loading">
        <h1 class="loading">Loading...</h1>
    </div>
    <div v-else>
        <p class="card-label">Advice # {{quote.id}}</p>
        <p class="card-quote">"{{quote.advice}}"</p>
    </div>
    <div class="pattern"></div>
    <div class="dice-wrap" @click="getQuote">
        <img class="dice" src="../assets/images/icon-dice.svg" alt="Click to switch quote">
    </div>
</div>
</template>

<script>
export default {
    name: 'ContentCard',
    data() {
        return {
            quote: [],
            loading: true
        }
    },
    methods: {
        async getQuote() {
            this.loading = true
            const delay = (ms = 2000) => new Promise(r => setTimeout(r, ms))
            await delay()
            const res = await fetch('https://api.adviceslip.com/advice')
            const data = await res.json()
            this.quote = data.slip
            this.loading = false
            console.log(this.quote.id)
            console.log(this.quote.advice)
        }
    },
    mounted() {
        this.getQuote()
    }
}
</script>

<style>
.card {
    width: 250px;
    height: auto;
    min-height: 330px;
    background: var(--color-bg-card);
    border-radius: 15px;
    padding: 40px 14px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.card-label {
    margin-bottom: 24px;
    text-transform: uppercase;
    color: var(--color-accent-neon);
}

.card-quote {
    font-size: var(--font-size-md);
    margin-bottom: 24px;
}

.pattern {
    content: '';
    background: url('../assets/images/pattern-divider-mobile.svg') center no-repeat;
    width: 100%;
    height: 16px;
    margin-bottom: 30px;
}

.dice-wrap {
    background: var(--color-accent-neon);
    width: 64px;
    height: 64px;
    border-radius: 50%;
    position: absolute;
    bottom: -30px;
    cursor: pointer;
}

.dice-wrap:hover {
    box-shadow: 0px 0px 40px #53FFAA;
}

.dice {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}

.loading {
    margin-bottom: 30px;
}


/* responsive styles */
@media screen and (min-width: 375px) {
    .card {
        width: 343px;
        height: auto;
        min-height: 315px;
        padding: 40px 24px;
    }
}

@media screen and (min-width: 768px) {
    .card {
        width: 540px;
        height: auto;
        min-height: 332px;
        padding: 48px;
    }

    .card-label {
        font-size: var(--font-size-sm);
    }

    .card-quote {
        font-size: var(--font-size-lg);
        margin-bottom: 40px;
    }

    .pattern {
        content: '';
        background: url('../assets/images/pattern-divider-desktop.svg') center no-repeat;
    }
}
</style>
