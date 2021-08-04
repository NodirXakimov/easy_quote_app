<template>
    <div class="card m-4 quote" style="width: 18rem;">
        <div class="card-body">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
}
</script>

<style scoped>
    .quote {
        font-family: 'Montserrat', sans-serif;
        cursor: pointer;
    }
    .quote:hover {
        background-color: antiquewhite;
    }
</style>