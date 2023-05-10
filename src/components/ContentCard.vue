<template>
<div class="card shadow">
    <p class="card-label">Advice #</p>
    <p class="card-quote">“It is easy to sit up and take notice, what's difficult is getting up and taking action.”</p>
    <img class="pattern" src="" alt="">
    <div class="dice-wrap">
        <img class="dice" src="../assets/images/icon-dice.svg" alt="Click to switch quote">
    </div>
</div>
</template>

<script>
export default {
    name: 'ContentCard'
}
</script>

<style>
.card {
    width: 250px;
    height: 330px;
    background: var(--color-card-bg);
    border-radius: 15px;
    padding: 40px 14px;
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
    content: url('../assets/images/pattern-divider-mobile.svg');
    zoom: 65%;
}

.dice-wrap {
    background: var(--color-accent-neon);
    width: 64px;
    height: 64px;
    border-radius: 50%;
    position: absolute;
    left: 93px;
    top: 298px;
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


/* responsive styles */
@media screen and (min-width: 375px) {
    .card {
        width: 343px;
        height: 315px;
        padding: 40px 24px;
    }

    .pattern {
        zoom: 1;
    }

    .dice-wrap {
        left: 139px;
        top: 283px;
    }
}

@media screen and (min-width: 768px) {
    .card {
        width: 540px;
        height: 332px;
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
        content: url('../assets/images/pattern-divider-desktop.svg')
    }

    .dice-wrap {
        left: 238px;
        top: 300px;
    }
}
</style>
