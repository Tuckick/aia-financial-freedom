<template>
  <div class="accordion-text-body">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'AccordionContentTextBody',
}
</script>

<style lang="scss">

.accordion-text-body {
  font-size: 14px;
  font-weight: 400;
  font-style: normal;
  margin: 0;
  color: hsla(0, 0%, 0%, 0.8);

  p {
    line-height: 1.9;
  }

  strong {
    font-weight: 500;
  }

  .list-bullet {
    li::before {
      content: '•';
      margin-left: -1em;
      display: inline-block;
      width: 1em;
    }
  }

  .list-bullet-sub {
    li::before {
      content: '-';
      margin-left: -1em;
      display: inline-block;
      width: 1em;
    }
  }
}
</style>
