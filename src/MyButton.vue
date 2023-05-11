<template>
    <button>
        <slot />
    </button>
</template>

<script setup lang="ts">
import type { ButtonHTMLAttributes } from 'vue'

// Ths code will throw error

interface MyButtonProps extends ButtonHTMLAttributes {
    variant: 'blue' | 'white'
}

/*
error during build:
Error: [@vue/compiler-sfc] Failed to resolve index type into finite keys

___masked__/vue-ts-bug/node_modules/@vue/runtime-dom/dist/runtime-dom.d.ts
1258|  }
1259|  type EventHandlers<E> = {
1260|      [K in keyof E]?: E[K] extends (...args: any) => any ? E[K] : (payload: E[K]) => void;
   |            ^^^^^^^
1261|  };
1262|  
*/

defineProps<MyButtonProps>()
</script>