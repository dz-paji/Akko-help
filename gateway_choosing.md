# 使用 ip route 更改网关

## 太长不想看

在 AkkoCloud, 如需切换出口网关, 您只需要输入下方对应命令即可。

### 切换至联通出口

``` bash
ip route add default via 218.98.26.161
```

### 切换至电信出口

``` bash
ip route add default via 180.97.193.1
```

### 切换至移动出口

``` bash
ip route add default via 223.111.183.65
```

## ip route 命令使用实例

### 列出路由

``` bash
ip route list
ip route show
ip route
```

### 查看指定网段的路由

``` bash
ip route list 10.0.0.0/24
```

### 追加路由

``` bash
ip route append 10.0.0.0/24 via 192.168.1.12 #追加一个指定网络的路由，为了平滑切换网关使用
```

`via` 参数后面跟网关

### 修改路由

``` bash
ip route change 10.0.0.0/24 via 192.168.1.11
ip route replace 10.0.0.0/24 via 192.168.1.111
```

### 删除路由

``` bash
ip route del 10.0.0.0/24 via 192.168.1.1
```

### 清空指定网段的路由

``` bash
ip route flush 10.0.0.0/24 #这个是清理所有192.168.2.0/24相关的所有路由，有时候设置错网关存在多条记录，就需要一次性清空相关路由再进行添加
```

### 添加默认路由

``` bash
ip route add default via 192.168.1.1
```

### 指定路由 metric

``` bash
ip route add 10.0.0.0/24 via 192.168.1.15 metric 10
```
