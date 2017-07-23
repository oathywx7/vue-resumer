<template>
    <div id="topbar">
        <div class="logo">
            logo
        </div>
        <div class="actions">
            <button id="registered">注册</button>
            <button id="input">登录</button>
        </div>
    </div>
</template>

<style >
  #topbar{
      
      display: flex;
      justify-content: space-between;
      padding: 20px;
  }
  #logo{}
  #actions{}
  #topbar >　#actions > #registered{
      list-style: none;
  }
</style>