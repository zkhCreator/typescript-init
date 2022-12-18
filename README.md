# 从 0 开始的 typescript 初始化工程

> 由于对于 TS 的初始化以及配置不是很熟悉，从0开始每一步执行对应的配置，每一步执行完成后以 git 的方式提交，并通过 commit 执行的方案。
> 同时在下面写下所有的操作步骤

- `npm init` 创建工程
- `npm install -D typescript` 以 devDependency 的方式安装 typscript，不会在打包后的产物中依赖。只是服务于 coding
- `npx tsc --init` 其中 tsc 为 typescirpt 的缩写
    - `npx` 为 `node` 内置命令，可以执行已经安装好的命令
- 在 `tsconfig.json` 中增加 exclude，即 typescript 不编译 的文件
    - 在 `tsconfig.json` 中的编译配置优先级为 `files > exclude > include`
- 创建 `src` 文件路径，并在 `src` 路径下创建 ts 工程文件 `index.ts`
