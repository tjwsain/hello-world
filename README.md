<a href="https://gohugo.io/"><img src="https://raw.githubusercontent.com/gohugoio/gohugoioTheme/master/static/images/hugo-logo-wide.svg?sanitize=true" alt="Hugo" width="565"></a>

一个快速、灵活的静态网站生成器，由 [bep](https://github.com/bep)、[spf13](http://spf13.com/) 及 [Hugo 社区贡献者](https://github.com/gohugoio/hugo/graphs/contributors) 倾力打造。

[官方网站](https://gohugo.io) |
[论坛](https://discourse.gohugo.io) |
[文档](https://gohugo.io/getting-started/) |
[安装指南](https://gohugo.io/getting-started/installing/) |
[贡献指南](CONTRIBUTING.md) |
[Twitter](https://twitter.com/gohugoio)

[![GoDoc](https://godoc.org/github.com/gohugoio/hugo?status.svg)](https://godoc.org/github.com/gohugoio/hugo)
[![Linux、MacOS 和 Windows 测试](https://github.com/gohugoio/hugo/workflows/Test/badge.svg)](https://github.com/gohugoio/hugo/actions?query=workflow%3ATest)
[![Go Report Card](https://goreportcard.com/badge/github.com/gohugoio/hugo)](https://goreportcard.com/report/github.com/gohugoio/hugo)

## 概览

Hugo 是一个使用 [Go][] 编写的静态 HTML 和 CSS 网站生成器。
它针对速度、易用性和可配置性进行了优化。
Hugo 接收包含内容和模板的目录，并将其渲染为完整的 HTML 网站。

Hugo 使用带有 front matter 元数据的 Markdown 文件，并且可以从任意目录运行。
这非常适合共享主机以及没有特权账户的环境。

Hugo 可以在不到一秒的时间内生成一个中等规模的网站。
通常情况下，每一份内容的渲染时间约为 1 毫秒。

Hugo 适用于各种类型的网站，包括博客、个人站点以及文档网站。

#### 支持的架构

目前，我们为 Windows、Linux、FreeBSD、NetBSD、DragonFly BSD、OpenBSD、macOS（Darwin）以及 [Android](https://gist.github.com/bep/a0d8a26cf6b4f8bc992729b8e50b480b) 提供预编译的 Hugo 二进制文件，支持 x64、i386 和 ARM 架构。

只要 Go 编译器工具链能够运行，Hugo 也可以从源代码编译，例如在 Plan 9 和 Solaris 等其他操作系统上进行编译。

**完整文档请参阅 [Hugo 文档](https://gohugo.io/getting-started/)。**

## 选择安装方式

如果你希望使用 Hugo 作为网站生成器，只需安装 Hugo 二进制文件即可。
Hugo 二进制文件没有外部依赖。

如果你希望参与 Hugo 源代码或文档的开发，建议先 [Fork Hugo GitHub 项目](https://github.com/gohugoio/hugo#fork-destination-box)，然后将其克隆到本地计算机。

最后，你也可以使用 `go` 安装 Hugo 源代码，自行构建二进制文件并运行 Hugo。
对于有经验的 Go 开发者来说，构建二进制文件非常简单。

### 将 Hugo 作为网站生成器安装（二进制安装）

请参阅 [Hugo 文档中的安装说明](https://gohugo.io/getting-started/installing/)。

### 从源代码构建并安装二进制文件（高级安装）

#### 前置工具

* [Git](https://git-scm.com/)
* [Go（我们使用最新的两个大版本进行测试；但请注意，Hugo 0.81.0 及以上版本需要 Go 1.16 或更高版本。）](https://golang.org/dl/)

#### 从 GitHub 获取源代码

从 Hugo 0.48 开始，Hugo 使用 Go 1.11 内置的 Go Modules 支持进行构建。最简单的方法是将 Hugo 克隆到 `GOPATH` 之外的目录，例如：

```bash
mkdir $HOME/src
cd $HOME/src
git clone https://github.com/gohugoio/hugo.git
cd hugo
go install
```

**如果你使用 Windows，请将上面的 `$HOME` 环境变量替换为 `%USERPROFILE%`。**

如果希望启用 Sass/SCSS 支持，请使用 `--tags extended`，并确保 Go 环境中设置了 `CGO_ENABLED=1`。如果不希望全局启用 CGO，也可以仅在编译 Hugo 时临时启用 CGO：

```bash
CGO_ENABLED=1 go install --tags extended
```

## Hugo 文档

Hugo 文档目前存放在独立的仓库中，详见 https://github.com/gohugoio/hugoDocs。不过，我们仍然通过 `git subtree` 在本仓库中保留了一份文档副本。要将 `/docs` 子目录构建为 Hugo 网站，需要先克隆本仓库：

```bash
git clone git@github.com:gohugoio/hugo.git
```

## 为 Hugo 做贡献

有关参与 Hugo 项目的完整指南，请参阅 [贡献指南](CONTRIBUTING.md)。

我们欢迎各种形式的贡献，包括文档、主题、组织工作、教程、博客文章、Bug 报告、Issue、功能请求、功能实现、Pull Request、在论坛回答问题、协助管理 Issue 等。

Hugo 社区和维护者都非常活跃，并且乐于提供帮助；项目也从这些持续不断的贡献中受益匪浅。

### 提出支持问题

我们拥有活跃的 [讨论论坛](https://discourse.gohugo.io)，用户和开发者可以在那里提问和交流。
请不要使用 GitHub Issue 来提出一般性的使用问题。

### 报告问题

如果你认为发现了 Hugo 或其文档中的缺陷，请使用 GitHub Issue 跟踪器向 Hugo 维护者报告。
如果你不确定这是否属于 Bug，可以先在 [讨论论坛](https://discourse.gohugo.io) 中询问。
报告问题时，请提供当前使用的 Hugo 版本（`hugo version`）。

### 提交补丁

Hugo 项目欢迎所有贡献者和贡献，无论技术水平或经验如何。
如果你希望参与贡献，我们会帮助你完成贡献流程。
Hugo 是一个非常活跃的项目，每天都有大量贡献产生。

我们希望为用户打造尽可能优秀的产品，同时为开发者提供尽可能好的贡献体验。
因此，我们制定了一套指导原则，以确保所有贡献都符合项目要求。
这些指导原则并不是为了筛选或阻碍贡献者参与项目。
如果你不熟悉贡献流程，Hugo 团队会帮助你，并指导你按照项目规范完成贡献。

有关贡献代码的完整指南，请参阅 [贡献指南](CONTRIBUTING.md)。

[Go]: https://golang.org/
[Hugo Documentation]: https://gohugo.io/overview/introduction/

## 依赖项

Hugo 的实现离不开众多优秀的开源库。

运行 `hugo env -v` 可以获得完整且最新的依赖列表。

在 Hugo 0.89.0 中，依赖列表按字典序排列如下：

```text
cloud.google.com/go/storage="v1.10.0"
cloud.google.com/go="v0.87.0"
github.com/Azure/azure-pipeline-go="v0.2.2"
github.com/Azure/azure-storage-blob-go="v0.9.0"
github.com/BurntSushi/locker="v0.0.0-20171006230638-a6e239ea1c69"
github.com/BurntSushi/toml="v0.3.1"
github.com/PuerkitoBio/purell="v1.1.1"
github.com/PuerkitoBio/urlesc="v1.1.3"
github.com/alecthomas/chroma="v0.9.4"
github.com/armon/go-radix="v1.0.0"
github.com/aws/aws-sdk-go="v1.41.14"
github.com/bep/debounce="v1.2.0"
github.com/bep/gitmap="v1.1.2"
github.com/bep/godartsass="v0.12.0"
github.com/bep/golibsass="v1.0.0"
github.com/bep/gowebp="v0.1.0"
github.com/bep/tmc="v0.5.1"
github.com/cli/safeexec="v1.0.0"
github.com/cpuguy83/go-md2man/v2="v2.0.0"
github.com/disintegration/gift="v1.2.1"
github.com/dlclark/regexp2="v1.4.0"
github.com/dustin/go-humanize="v1.0.0"
github.com/evanw/esbuild="v0.13.12"
github.com/fsnotify/fsnotify="v1.5.1"
github.com/getkin/kin-openapi="v0.80.0"
github.com/ghodss/yaml="v1.0.0"
github.com/go-openapi/jsonpointer="v0.19.5"
github.com/go-openapi/swag="v0.19.5"
github.com/gobuffalo/flect="v0.2.3"
github.com/gobwas/glob="v0.2.3"
github.com/gohugoio/go-i18n/v2="v2.1.3-0.20210430103248-4c28c89f8013"
github.com/gohugoio/locales="v0.14.0"
github.com/gohugoio/localescompressed="v0.14.0"
github.com/golang/groupcache="v0.0.0-20200121045136-8c9f03a8e57e"
github.com/golang/protobuf="v1.5.2"
github.com/google/go-cmp="v0.5.6"
github.com/google/uuid="v1.1.2"
github.com/google/wire="v0.4.0"
github.com/googleapis/gax-go/v2="v2.0.5"
github.com/googleapis/gax-go="v2.0.2+incompatible"
github.com/gorilla/websocket="v1.4.2"
github.com/inconshreveable/mousetrap="v1.1.0"
github.com/jdkato/prose="v1.2.1"
github.com/jmespath/go-jmespath="v0.4.0"
github.com/kyokomi/emoji/v2="v2.2.8"
github.com/mailru/easyjson="v0.0.0-20190626092158-b2ccc519800e"
github.com/mattn/go-ieproxy="v0.0.1"
github.com/mattn/go-isatty="v0.0.14"
github.com/mattn/go-runewidth="v0.0.5"
github.com/miekg/mmark="v1.3.0"
github.com/mitchellh/hashstructure="v1.1.0"
github.com/mitchellh/mapstructure="v1.4.2"
github.com/muesli/smartcrop="v0.3.0"
github.com/niklasfasching/go-org="v1.5.0"
github.com/olekukonko/tablewriter="v0.0.5"
github.com/pkg/errors="v0.9.1"
github.com/rogpeppe/go-internal="v1.8.0"
github.com/russross/blackfriday/v2="v2.0.1"
github.com/russross/blackfriday="v1.5.3-0.20200218234912-41c5fccfd6f6"
github.com/rwcarlsen/goexif="v0.0.0-20190401172101-9e8deecbddbd"
github.com/sanity-io/litter="v1.1.0"
github.com/sass/libsass="3.6.5"
github.com/shurcooL/sanitized_anchor_name="v1.0.0"
github.com/spf13/afero="v1.6.0"
github.com/spf13/cast="v1.4.1"
github.com/spf13/cobra="v1.2.1"
github.com/spf13/fsync="v0.9.0"
github.com/spf13/jwalterweatherman="v1.1.1"
github.com/spf13/pflag="v1.2.1"
github.com/tdewolff/minify/v2="v2.9.22"
github.com/tdewolff/parse/v2="v2.5.21"
github.com/webmproject/libwebp="v1.2.0"
github.com/yuin/goldmark-highlighting="v0.0.0-20200307114337-60d527fdb691"
github.com/yuin/goldmark="v1.4.2"
go.opencensus.io="v0.23.0"
gocloud.dev="v0.20.0"
golang.org/x/image="v0.0.0-20210220032944-ac19c3e999fb"
golang.org/x/net="v0.0.0-20210614182718-04defd469f4e"
golang.org/x/oauth2="v0.0.0-20210628180205-a41e5a781914"
golang.org/x/sync="v0.0.0-20210220032951-036812b2e83c"
golang.org/x/sys="v0.0.0-20210908233432-aa78b53d3365"
golang.org/x/text="v0.0.0-20210906153134-8f4f6e5e"
golang.org/x/xerrors="v0.0.0-20200804184101-5ec99f83aff1"
google.golang.org/api="v0.51.0"
google.golang.org/genproto="v0.0.0-20210716133855-ce7ef5c701ea"
google.golang.org/grpc="v1.39.0"
google.golang.org/protobuf="v1.27.1"
gopkg.in/yaml.v2="v2.4.0"
```