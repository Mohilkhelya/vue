<template>
    <div class="card">
        <div id="card-header">
            <slot name="header"></slot>
        </div>
        <div id="card-content">
            <slot></slot>
        </div>
        <div id="card-footer">
            <slot name="footer"></slot>
        </div>
    </div>
</template>

<script>
    export default {
        name:'Card',
    }
</script>

<style scoped>
.card{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2) ;
    transition: 0.3s;
    padding: 30px;
    width: 300px;
    margin: auto;
    margin-top: 4vw;
    opacity: 0.7;
}

.card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.27) ;
    opacity: 1;
}
</style>