<template>
    <div class="footer">
        <p>Challenge by <a href="https://www.frontendmentor.io" target="_blank">Frontend Mentor</a> 🤍 Coded by <a href="https://www.nityagulati.com" target="_blank">Nitya Gulati</a>.</p>
    </div>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style>
.footer {
    position: absolute;
    bottom: 20px;
}

a {
    color: var(--color-text);
}

a:hover {
    color: var(--color-accent-muted);
}
</style>
