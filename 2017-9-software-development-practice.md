## 2017 秋季技术分享
#### [软件开发工程化思考与实践「乱炖」](http://slides.maples7.com/2017-9.html)
<br />
<p>
  <small>by <a target="_blank" href="http://maples7.com">Maples7</a></small><br />
	<small>2017.9</small>
</p>



## 1. 选择编辑器


- Editor or IDE? <!-- .element: class="fragment" data-fragment-index="1" -->

- Vim and Emacs <!-- .element: class="fragment" data-fragment-index="2" -->

- <!-- .element: class="fragment" data-fragment-index="3" --> [VSCode](https://code.visualstudio.com/) <!-- .element: class="fragment" data-fragment-index="3" -->

Note:
一个跟「世界上最好的语言是什么」一样可以引发社区「战争」的话题。
其实没有太多可以说的东西，更多只是被安利之后自己在使用过程中去体会，「如人饮水，冷暖自知」。

IDE or Editor? 之前也喜欢高大全的东西——用 VS，什么语言写起来都很爽。后来慢慢开始喜欢小而美的东西，一个个小而专一的组件，经过人为的合理编排，像搭乐高一样搭起来，每个组件都发挥它最大的价值。
软件工程很多时候也是如此，核心在于选择符合实际情况的东西，每一个组件都各有各的特点，它们也是各种权衡、各种做 trade-off 的结果，就像 IDE 功能全面省心，但是启动速度就比较慢，很多功能其实可能永远都用不到，那这些用不到的部分其实在你实际使用的过程中不但不会成为优势，反而会成为一种负担。写代码的追求也是如此，每一行代码都发挥它们最大的价值，找到一个抽象层级平衡的点，不多不少。

上古时代的神器：Vim and Emacs，编辑器之神 和 神的编辑器。在服务器环境用得到，还需更多的学习和使用。

VSCode：2016.3 推出 1.0 版本，上手简单，使用 Electron 技术，继承的是 Web 开发的理念而不是桌面端开发的理念，所以迭代更新速度很快。使用过程中慢慢熟悉快捷键，选择一些合适的插件。尤其适合前端开发。


![最喜欢的 IDE 投票](resource/img/vscode1.PNG "最喜欢的 IDE 投票")

Note:
justjavac（上一周刚生了一个女儿）拉的一个 Node 开发群的投票。


![VSCode Usage](resource/img/vscode-usage.gif "VSCode Usage Gif")



## 2. Tips for [Node](https://nodejs.org/) Development


### [Prettier](https://github.com/prettier/prettier)
<br />
"Prettier is an opinionated code formatter."

"Prettier enforces a consistent code style across your entire codebase."

Note:
会解析抽象语法树（AST）然后 re-print，保证同样的代码会有同样的 format。


### [nvm](https://github.com/creationix/nvm) + [nrm](https://github.com/Pana/nrm)
<br />
"Node Version Manager - Simple bash script to manage multiple active node.js versions"

"NPM registry manager, fast switch between different registries: npm, cnpm, nj, taobao"


### [husky](https://github.com/typicode/husky)
<br />
"Git hooks made easy"

"Husky can prevent bad commit, push and more 🐶 woof!"

Note:
pre-commit hook 保证提交之前运行 lint/format/test，防止坏代码污染远端代码库。
传统手动写 git pre-commit hook 的问题是针对个人本地的，无法与团队共享，尤其是如果项目中期再加入，还可能遭到团队排斥。
husky 在 npm install 的时候注入 hook。



## 3. Tips for [Python](https://www.python.org/) Development


### [YAPF](https://github.com/google/yapf)
<br />
"In essence, the algorithm takes the code and **reformats it to the best formatting** that conforms to the style guide, even if the original code didn't violate the style guide."


### [Anaconda](https://www.anaconda.com/distribution/)?
## Give [pyenv](https://github.com/pyenv/pyenv) + [pipenv](https://github.com/kennethreitz/pipenv) a chance...

Note:
- pyenv 相当于 nvm，在同一个主机上管理 Python 的多个版本环境。
- pipenv 相当于 npm，但是还可以为每个项目建立独立的运行环境。会生成一个类似于 package.json 的文件声明项目依赖，用同样的工具就可以多平台移植，直接 `pipenv install` 一下就可以了。



## 4. A Few Solid Universal Development Tools


## [codelf](https://unbug.github.io/codelf/)
<br />
### There are only two hard things in Computer Science: cache invalidation and naming things.
#### —— Phil Karlton

Note:
注意右上角还可以管理你的 GitHub 上 Star 过的项目，可以分组、可以加标签等等。


## [devdocs.io](http://devdocs.io/)

Note:
类似于 macOS 上的 Dash，文档的集合，还有版本管理，告别一大堆零散的浏览器书签。


## [Github Gist](https://gist.github.com/)

Note:
简洁高效的随手记录工具



## 5. How to write a pretty README


### [art-of-readme](https://github.com/noffle/art-of-readme)


- Your job is to:

    1. tell them what it is (with context)
    2. show them what it looks like in action
    3. show them how they use it
    4. tell them any other relevant details

Note:
另外，写 README 要照顾到阅读者的「认知漏斗」，从上往下逐步出现越来越详尽的细节。Celery 的文档写的中规中矩，但这一点上做得不是很好。


- Checklist:

    - One-liner explaining the purpose of the module
    - Necessary background context & links
    - Potentially unfamiliar terms link to informative sources
    - Clear, runnable example of usage
    - Installation instructions
    - Extensive API documentation
    - Performs cognitive funneling
    - Caveats and limitations mentioned up-front
    - Doesn't rely on images to relay critical information
    - License

Note:
- 一句话解释模块的目的
- 必要的背景资料或链接
- 为潜在不熟悉的术语提供到信息来源的链接
- 简洁可运行的实例
- 安装说明
- 详细的API文档
- 对认知漏斗的执行
- 前面提到的注意事项和限制
- 不要依赖图片传递关键信息
- 许可证


### [common-readme](https://github.com/noffle/common-readme)

Note:
根据 pacakge.json 里的信息自动生成一个良好结构的 README 模板



## 「编译时」与「运行时」




## Thank You
#### [maples7.com](http://maples7.com)
