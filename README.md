# 轻量级部署工具

## 使用

### 安装
```shell
npm i deploy-fish -D

```

### 配置
```ts

// deploy.config.prod.ts
// deploy.config.test.ts
// deploy.config.dev.ts
import { defineConfig } from 'deploy-fish'

export default defineConfig({
  ssh: {
    host: '172.16.20.150',
    username: 'root',
    password: 'xxx',
    port: 22
  },
  project: {
    // 本地项目打包产物所在目录
    distDir: 'dist',
    // 对应服务器上项目所在目录
    serverWebDir: '/root/test'
  }
})
```

```json
// package.json
{
  "scripts": {
    "deploy": "light-deploy --mode test",
  }
}

```

- `deploy.config.[mode].ts`文件名中的`[mode]` 和 `package.json` 中的 `light-deploy --mode [mode]` 保持一致