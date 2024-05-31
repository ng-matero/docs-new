# 添加项目

使用 `ng add` 命令可以快速创建项目目录，并且可以通过 CLI 选项配置 ng-matero 的主题风格等。

1、必须创建一个 Angular 项目，建议采用 CLI 版本（17.x）创建，低版本可能会有兼容问题。

> 最新 `Angular 18` 将会在不久支持

```bash
$ ng new <project-name>
$ cd <project-name>
```

> CSS 预处理器最好选择 Scss (Sass)，使用其它预处理器则无法使用 Angular Material 及 ng-matero 提供的样式变量。

2、添加 ng-matero

```bash
$ ng add ng-matero
```

## 初始化选项

在添加项目的时候会有预构建选项，它可以更快速地定制主题。

![](../.gitbook/assets/project-init.png)

*   Choose a prebuilt layout template (选择布局模板类型)

    - `static`: 表示静态模板，项目启动后无法再通过 `options` 更改布局样式
    - `dynamic`: 保留了所有布局参数，项目启动后可以通过 `options` 动态更改布局，比如演示示例就是这种方式。
*   Choose a prebuilt navigation type (选择导航类型)

    - `side`: 侧边栏导航
    - `top`: 顶部导航
*   Choose a prebuilt theme style (选择主题风格)

    - `Auto`: 根据系统
    - `light`: 明亮主题
    - `dark`: 暗黑主题
*   Choose a prebuilt direction option (选择文字方向)

    - `ltr`: 从左到右
    - `rtl`: 从右到左
*   Include the Angular animations module? (是否包含Angular动画模块？)

    - `Include and enable animations`: 包含并启用动画
    - `Include, but disable animations`: 包含但禁用动画
    - `Do not include`: 不包含
