# vuex持久化

## 手动利用HTML5的本地存储
```js
//在页面加载时读取sessionStorage里的状态信息
if (sessionStorage.getItem('store')) {
  store.replaceState(
    Object.assign(
      store.state,
      JSON.parse(sessionStorage.getItem('store'))
    )
  )
}
//在页面刷新时将vuex里的信息保存到sessionStorage里
window.addEventListener('beforeunload', () => {
  sessionStorage.setItem('store', JSON.stringify(store.state))
})
```

## vuex-persistedstate
可以通过vuex-persistedstate插件实现，但注意只有在state被修改的时候才会触发插件，并且`state被actions修改`的时候是不会触发的。