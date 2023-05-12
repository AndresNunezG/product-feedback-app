<template>
  <div class="badge-dashboard">
    <h1 class="badge-title">Fancy App 🫧</h1>
    <p class="badge-subtitle">Feedback Board</p>
    <small class="badge-credits">credits: frontendmentor.io</small>
  </div>
</template>

<style lang="css">
.badge-dashboard {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-end;
  height: 120px;
  padding: 1rem;
  margin: 1rem;
  background-color:#99f1ff;
  background-image:
    radial-gradient(at 53% 77%, hsla(228,67%,70%,1) 0px, transparent 50%),
    radial-gradient(at 34% 5%, hsla(227,99%,72%,1) 0px, transparent 50%),
    radial-gradient(at 56% 66%, hsla(227,97%,75%,1) 0px, transparent 50%),
    radial-gradient(at 41% 98%, hsla(128,68%,66%,1) 0px, transparent 50%),
    radial-gradient(at 17% 80%, hsla(350,94%,76%,1) 0px, transparent 50%),
    radial-gradient(at 63% 68%, hsla(281,76%,75%,1) 0px, transparent 50%),
    radial-gradient(at 67% 36%, hsla(351,95%,77%,1) 0px, transparent 50%);
  border-radius: 12px;
  transition: filter 300ms;
  cursor: pointer;
}
.badge-dashboard:hover {
  filter: drop-shadow(0 0 2em hsla(228,67%,70%,1));
}
.badge-title,
.badge-subtitle,
.badge-credits {
  color: rgb(255, 255, 255);
}
.badge-title {
  font-weight: bold;
  font-size: 1.5rem;
  margin: 0;
}
.badge-subtitle {
  margin: 0;
}
.badge-credits {
  opacity: 0.8;
}
</style>
