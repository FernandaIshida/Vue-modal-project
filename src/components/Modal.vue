<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <slot>default content</slot> 
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [ 'theme' ],
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
.modal p {
    font-style: normal;
}
.modal actions {
    text-align: center;
    margin: 1.875rem 0 .625rem 0;
}
.modal .actions a {
    color: #333;
    padding: .5rem;
    border: .0625rem solid #eee;
    border-radius: .25rem;
    text-decoration: none;
    margin: .625rem;
}
.modal.sale {
    background: crimson;
    color: white;  
}
.modal.sale h1 {
    color: white;
}
.modal.sale .action {
    color: white;
}
.modal.sale .actions a{
    color: white;
}
</style>