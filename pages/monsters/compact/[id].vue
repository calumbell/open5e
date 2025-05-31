<script setup lang="ts">
import { navigateTo } from 'nuxt/app';
import { definePageMeta } from 'nuxt/dist/pages/runtime';

// Register middleware with page metadata
definePageMeta({
  middleware: [
    function (to) {
      return navigateTo(
        {
          path: `/monsters/${to.params.id}`,
          query: {
            mode: 'compact',
          },
        },
        {
          replace: true,
          redirectCode: 301,
        },
      );
    },
  ],
});
</script>
