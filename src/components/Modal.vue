<template>
    <div class="backdrop">
        <div class="modal">
            <p>modal content</p>
        </div>
    </div>
</template>

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
h1 {
    color: #03cfb4;
    border: none;
    padding: 0;

}
</style>