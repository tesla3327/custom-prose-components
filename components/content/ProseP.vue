<template>
  <div
    class="cursor-pointer transition-all duration-150 ease-in-out"
    :class="{
      'bg-yellow-100 rounded-md px-3 -mx-3': highlight,
      'opacity-30 ': hide,
    }"
    @click="toggleHighlight"
  >
    <p>
      <slot />
    </p>
  </div>
</template>

<script setup>
// Get a "hash" of the content
const slots = useSlots();
const hash = computed(() => {
  return (
    slots
      // Get the default slot
      .default()

      // Get the text from each node
      .map((slot) => {
        return slot.children;
      })
      .filter((text) => typeof text === 'string')

      // Combine the first letters of each word
      .map((text) =>
        text
          .split(' ')
          .map((word) => word[0])
          .join('')
      )
      .join('')
  );
});

const route = useRoute();
const highlight = ref(false);
const hide = ref(false);

// We need to rely entirely on side-effects here because
// the hash doesn't exist on the server
watch(
  () => route.hash,
  () => {
    console.log(route.hash);
    checkHash();
  }
);
onMounted(() => {
  checkHash();
});

const checkHash = () => {
  const isHighlighted = (highlight.value =
    route.hash === `#${hash.value}`);

  if (!isHighlighted && route.hash) {
    hide.value = true;
  } else {
    hide.value = false;
  }

  highlight.value = isHighlighted;
};

async function toggleHighlight() {
  if (highlight.value) {
    await navigateTo({ hash: '' }, { replace: true });
  } else {
    await navigateTo(
      { hash: `#${hash.value}` },
      { replace: true }
    );
  }

  checkHash();
}
</script>
