<template>
    <div v-if="hasErrors">
        <div class="font-medium text-red-600">
            Whoops! Something went wrong.
        </div>

        <ul class="mt-3 list-inside list-disc text-sm text-red-600">
            <li v-for="(error, key) in errors" :key="key">{{ error }}</li>
        </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'JetValidationErrors',
    computed: {
        errors(): Object {
            return this.$page.props.errors;
        },

        hasErrors(): boolean {
            return Object.keys(this.errors).length > 0;
        },
    },
});
</script>
