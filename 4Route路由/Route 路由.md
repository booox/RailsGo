# Route 路由

## 路由写法
```
resources :users, only: [:index, :show]  #Rest只生成 index 与 show 路由

resources :products, except: [:destroy]  #生成不包括 destroy
```
