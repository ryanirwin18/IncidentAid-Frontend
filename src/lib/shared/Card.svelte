<div class="card">
  <slot></slot>
</div>

<style>
  .card{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 672px;
    background: #D9D9D9;
    border-radius: 20px;
    margin-top: 15px;
  }
</style>