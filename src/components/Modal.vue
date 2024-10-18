<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header', 'text', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }

}

</script>

<style>
.modal {
    width: 25rem;
    padding: 1.25rem;
    margin: 6.25rem auto;
    background: white;
    border-radius: .625rem;
}
.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
}
.modal h1 {
    color: #03cfb4;
    border: none;
    padding: 0;

}

.modal.sale {
    background: crimson;
    color: white;  
}
.modal.sale h1 {
    color: white;
}
</style>