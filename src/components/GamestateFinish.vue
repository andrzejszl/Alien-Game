<template>
    <div class="modal" :class="uiState === 'lost' ? 'lost' : ''">
        <h2>You {{uiState}}!</h2>
        <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 131 131"
            aria-labelledby="face"
            role="presentation"
            width="70"
            height="70"
            >
            <title id="face">Face Icon</title>
            <defs>
            </defs>
            <circle class="cls-1" cx="65.5" cy="65.5" r="64" />
            <circle class="cls-2" cx="95" cy="65.8" r="7.5" />
            <circle class="cls-2" cx="36" cy="65.8" r="7.5" />
            <path
                class="cls3"
                d="M51,97s6,10,23,10S95,97,95,97"
                transform="translate(-8.5 -5.5)"
            />
        </svg>

        <button @click="resetGame">Let's play again!</button>
    </div>
</template>

<script>
    export default {
        props: ['uiState'],
        methods: {
            resetGame() {
                this.$store.commit('resetGame')
                },
        }
    }
</script>

<style lang="scss" scoped>
.modal {
    width: 480px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.modal.lost .cls3 {
    rotate: 180deg;
    transform-origin: 50% 50%;
}
.cls-1 {
      fill: #fbb040;
      stroke: #231f20;
      }

      .cls-1,
      .cls-3 {
      stroke-miterlimit: 10;
      stroke-width: 3px;
      }

      .cls-2 {
      fill: #231f20;
      }

      .cls-3 {
      fill: none;
      stroke: #be1e2d;
      }
</style>