<h1 align="center">sett-torrent-component-rule</h1>

---

<h4 align="center">这里会收录一些各磁力站点的规则</h4>

### 如何使用配置文件

---

> 前提是你可以使用 [sett-torrent-component](https://github.com/sayokey/sett-torrent-component)

1. 首先你可以在该仓库中寻找你需要的配置文件
2. 复制该配置文件的内容
3. 将它粘贴到你在 [sett-torrent-component](https://github.com/sayokey/sett-torrent-component) 中配置的规则文件中

### 做出贡献

---

> 将你的规则提交到本仓库

1. Fork 本仓库
2. 创建你的分支
3. 提交你的更改
4. 推送到分支
5. 创建一个新的 Pull Request
6. 等待审核

> 提交ISSUES

- 修正配置文件的错误
- 提出建议
- 反馈BUG

### 演示

---

这是一个在某站点的一个搜索和查看详细信息的规则

```json
  {
    "site": "cilisousuo",
    "searchUrl": "https://www.cilisousuo.com/search?q=${keyword}",
    "group": "//html/body/div[2]/ul",
    "count" : 50,
    "groupStart": 1,
    "page": "",
    "size" : "/li[${index}]/div[2]/text()",
    "name": "/li[${index}]/div[1]/div[1]/text()",
    "update": "/html/body/div[2]/div[2]/dl/dd[2]/text()",
    "magnet": "//*[@id=\"input-magnet\"]/@value",
    "detailUrl": "/li[${index}]/a/@href",
    "detail": {
      "enable": true,
      "url": "https://www.cilisousuo.com${detailUrl}",
      "size" : "/html/body/div[2]/div[2]/dl/dd[3]/text()",
      "name": "/html/body/div[2]/h1/text()",
      "update": "/html/body/div[2]/div[2]/dl/dd[2]/text()",
      "magnet": "//*[@id=\"input-magnet\"]/@value"
    },
    "proxy": {
      "host": "127.0.0.1",
      "port": 7890,
      "enable": true
    }
  }
```

首先你需要复制他，然后打开你在 [sett-torrent-component](https://github.com/sayokey/sett-torrent-component) 中`application.yml`配置的规则文件中,注意他是一个json数组
你需要将这个规则粘贴到数组中，然后保存

```json
[
  // 其他配置....
  {
    "site": "cilisousuo",
    "searchUrl": "https://www.cilisousuo.com/search?q=${keyword}",
    "group": "//html/body/div[2]/ul",
    "count" : 50,
    "groupStart": 1,
    "page": "",
    "size" : "/li[${index}]/div[2]/text()",
    "name": "/li[${index}]/div[1]/div[1]/text()",
    "update": "/html/body/div[2]/div[2]/dl/dd[2]/text()",
    "magnet": "//*[@id=\"input-magnet\"]/@value",
    "detailUrl": "/li[${index}]/a/@href",
    "detail": {
      "enable": true,
      "url": "https://www.cilisousuo.com${detailUrl}",
      "size" : "/html/body/div[2]/div[2]/dl/dd[3]/text()",
      "name": "/html/body/div[2]/h1/text()",
      "update": "/html/body/div[2]/div[2]/dl/dd[2]/text()",
      "magnet": "//*[@id=\"input-magnet\"]/@value"
    },
    "proxy": {
      "host": "127.0.0.1",
      "port": 7890,
      "enable": true
    }
  }
]
```