<template>
  <div class="roadmap-widget">
    <div class="roadmap-title">
      <h3>Roadmap</h3>
      <a>View</a>
    </div>
    <div class="roadmap-body">
      <div class="roadmap-item">
        <div class="item-label">
          <span class="item-dot item-dot--planned"></span>
          <span class="item-status">Planned</span>
        </div>
        <span class="item-amount">2</span>
      </div>
      <div class="roadmap-item">
        <div class="item-label">
          <span class="item-dot item-dot--progress"></span>
          <span class="item-status">In-Progress</span>
        </div>
        <span class="item-amount">3</span>
      </div>
      <div class="roadmap-item">
        <div class="item-label">
          <span class="item-dot item-dot--live"></span>
          <span class="item-status">Live</span>
        </div>
        <span class="item-amount">1</span>
      </div>
    </div>
  </div>
</template>

<style lang="css" scoped>
.roadmap-widget {
  background-color: white;
  border-radius: 12px;
  padding: 1rem;
  margin: 1rem;
}
.roadmap-title {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.roadmap-item {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
.item-label {
  display: flex;
  align-items: center;
  justify-content: flex-start;
}
.item-dot {
  display: block;
  width: 5px;
  height: 5px;
  margin-right: 5px;
  border-radius: 50%;
}
.item-dot--planned {
  background-color: rgb(232, 162, 138);
}
.item-dot--progress {
  background-color: rgb(160, 46, 247);
}
.item-dot--live {
  background-color: rgb(120, 186, 247);
}
.item-status {
  color: rgb(133, 142, 168);
}
.item-amount {
  font-weight: bold;
  color: rgb(133, 142, 168);
}
</style>
