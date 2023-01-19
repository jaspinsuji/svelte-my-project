<script>
    import { once, prevent_default } from "svelte/internal";


    // once - makes sure the event can only fire once(Remove handlers)
    // prevent_default - prevent default actions (e.prevent_default)
    // self - only fires the event if the click element is the target
   export let showModal = false;
    export let isPromo =false;
</script>
{#if showModal}
<div class="backdrop" class:promo={isPromo} on:click self>
    <div class="modal">
        <slot name="title"></slot>
        <p>Hey there ...</p>
        <slot></slot>
    </div>
</div>
{/if}

<main>

</main>
<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0,0.8);
    }
    .modal {
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background: white;
    }
</style>