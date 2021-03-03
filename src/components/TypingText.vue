<template>
    <div class="flex">
        <h1 ref="visibleText" :class="textClasses">{{ currentTypedText }}</h1>
        <div v-show="cursorVisible" :key="forceRedrawCursor" class="border-l-8 border-black" :style="{ height: textHeight }"></div>
    </div>
</template>

<script>
    export default {
        name: 'TypingText',
        props: {
            textToType: {
                type: String,
                required: true
            },
            textClasses: {
                type: String,
                required: false
            }
        },
        data() {
            return {
                currentTypedText: '',
                currentTypedIndex: 0,
                textHeight: 0,
                forceRedrawCursor: 0,
                cursorVisible: true,
                typingInterval: null
            };
        },
        mounted() {
            this.typingInterval = setInterval(this.typeFunction, 100);

            setInterval(this.blinkCursor, 500);
        },
        methods: {
            typeFunction() {
                if (this.textToType === this.currentTypedText) {
                    clearInterval(this.typingInterval);

                    return;
                }

                if (this.textHeight === 0) {
                    this.textHeight = this.$refs.visibleText.clientHeight;
                    this.forceRedrawCursor++;
                }

                this.currentTypedText += this.textToType.charAt(this.currentTypedIndex);
                this.currentTypedIndex++;
            },
            blinkCursor() {
                this.cursorVisible = !this.cursorVisible;
            }
        }
    };
</script>
