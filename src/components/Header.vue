<template>
  <div class="wrapper">
    <span>Simple Word Counter</span>
    <span>
      <a href="https://github.com/razinj/simple-word-counter-vue" target="_blank" rel="noopener noreferrer">
        Git Repository
      </a>
    </span>
  </div>
</template>

<style scoped>
.wrapper {
  height: 50px;

  display: flex;
  justify-content: space-between;
  align-items: center;

  border-bottom: 1px solid lightgray;
}

.wrapper::before {
  content: '';
  flex: 1;
}

.wrapper span:first-child {
  flex: 1;
}

.wrapper span:last-child {
  margin-right: 10px;
}

.wrapper span {
  user-select: none;
}

@media only screen and (max-width: 600px) {
  .wrapper::before {
    content: none;
  }

  .wrapper::before,
  .wrapper span:first-child {
    flex: none;
  }

  .wrapper span:first-child {
    margin-left: 10px;
  }

  .wrapper span:last-child {
    margin-right: 10px;
  }
}
</style>
