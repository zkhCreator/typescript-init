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
- 安装 `npm install -D @types/node`，安装 `@types/node` 创建 node 的 typescript 版本，方便类型依赖。
- `npm install -D ts-node` 安装 ts-node，用于运行 ts 编译 + 执行。类似于服务端能正常跑 node 服务
    - `npx ts-node index.ts` 通过 npx 来执行 typescript 的调用
    - 针对不同环境可以通过 `npx ts-node --project tsconfig.json src/index.ts` 来根据不同的 `tsconfig.json` 配置进行执行
    - `tsconfig.json` 中的 `rootDir` 不执行 ts-node 的执行路径，仅影响 `tsc` 编译的路径
- 通过增加 launch.json 配置调试能力。
    - runtimeArgs 用于对于 node 的 params 参数设置
    - args 是传参数
- 增加动态加载的能力
    - 通过 `npm install -D nodemon` 引入 nodemon，这里不调用 `@types/nodemon` 是因为这个命令我们是用于外部调用，不需要在代码中进行调用。
    - 通过 `nodemon.json` 来配置 `nodemond` 需要监听的位置，以及需要执行的命令