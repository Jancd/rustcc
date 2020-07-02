# 微软对 Rust 的热爱是怎么回事？

> * 原文地址：https://visualstudiomagazine.com/articles/2020/06/02/rust-love.aspx?m=1
> * 原文作者：David Ramel (06/02/2020)
> * 译者：【 [Jancd](https://github.com/Jancd/) 】
> * 校对：【 [Rust 日报小组](https://rustcc.cn/section?id=f4703117-7e6b-4caf-aa22-a3ad3db6898f) 】

---

微软已经管理了几种流行的编程语言 - C＃，TypeScript，F＃，那为什么微软也和广大开发者一样也喜欢 Rust 呢？

![](https://visualstudiomagazine.com/articles/2020/06/02/~/media/ECG/visualstudiomagazine/Images/introimages2014/0715vsm_PardasaniInDepth.ashx)

举个栗子，去年 C++ 内存崩溃的 bug 促使微软[将 Rust 视为底层系统编程的替代方案](https://visualstudiomagazine.com/articles/2019/07/18/microsoft-eyes-rust.aspx)。

就在上周【译注：原文发布日期为 06/02/2020 】，Stack Overflow 发布了最新版本的大型[开发者调查报告](https://visualstudiomagazine.com/articles/2020/05/28/so-2020-survey.aspx)，该调查报告指出 Rust 连续第五年被评为“最受欢迎”的编程语言。这是对使用某种语言进行开发，并表示有兴趣继续使用该语言的受访者所占百分比的一种度量。

并且有一位开发者在 Stack Overflow 调查报告[评论区](https://stackoverflow.blog/2020/05/27/2020-stack-overflow-developer-survey-results/)中写道：“如果你喜欢 C++，那么你会爱上 Rust！”。

![](https://visualstudiomagazine.com/articles/2020/06/02/~/media/ECG/visualstudiomagazine/Images/2020/06/so_most_loved_languages.asxh)

令人惊讶的是，Stack Overflow 指出“参加调查的大多数开发人员都不熟悉该语言”，在流行度方面，Rust 在 Stack Overflow 列表中排名第 19 位。所以，尽管它无疑是 Stack Overflow 用户群体中“最受欢迎”的语言，但了解或使用它的人并不多。这也是个问题。

与此同时，就在今天【译注：2020 年 6 月 2 号】，Rust [进入了 TIOBE 指数的前 20 名](https://visualstudiomagazine.com/articles/2020/06/02/tiobe-june-2020.aspx)，它从第 38 位跃升到第 20 位，跃升了惊人的 18 位，这其实是挺罕见的。

![Most Loved Programming Languages](https://visualstudiomagazine.com/articles/2020/06/02/~/media/ECG/visualstudiomagazine/Images/2020/06/tiobe_rust.asxh)

以下是 [TIOBE](https://www.tiobe.com/tiobe-index/) 对上述一些发展的看法:

> 主要原因是 Rust 是一种正确的系统编程语言。Rust 在静态强类型化的同时，解决了其他编程语言的冗余编程和一些尖锐问题。它的类型系统防止运行时空指针异常，并且他的内存管理是在编译期间计算完成的，因此也没有垃圾回收带来的问题。我们曾尝试使用 D，Lua 和 Julia 试图击败 C/C++，但只有 Rust 是第一个真正接近这个目标的。让我们看看 Rust 能否在未来几年保持前 20 的位置。

那 Stack Overflow 是怎么看待的呢？在这次调查发布之前，Rust 仅仅是连续第四年成为“最受喜爱”的语言，Stack Overflow 在一篇题为“[什么是 Rust，为什么它这么受欢迎](https://stackoverflow.blog/2020/01/20/what-is-rust-and-why-is-it-so-popular/)”的文章中对这一现象进行了深入剖析。

这是 Stack Overflow 的 TL;DR：

>Rust 保证了性能、可控、内存安全和无畏并发 — 这是一个诱人的组合，尤其是对于系统编程而言。它还将一些有趣的特性(如仿射类型（affine types）和卫生宏（hygienic macro）引入了主流论述。加上 Rust 本身开放的开发过程，许多程序员（甚至那些不使用它的程序员）对 Rust 的高度尊重是有道理的。

与此同时，对于微软来说，这一切都是为了漏洞安全以及避免那些讨厌的 CVEs([Common Vulnerabilities and Exposures，即常见的漏洞和披露](https://en.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures))。微软安全响应中心团队发现：“大多数修复的漏洞和分配的 CVE 是由开发人员无意中在其 C 和 C++ 代码中写了内存错误的 bug 所引起的。”

这促使团队寻找 C++ 的替代品，C++ 已被用于编写系统软件，以及一些微软产品，如各种 Windows 版本、Visual Studio、Office、Internet Explorer等。

微软 MSRC 团队在 [2019 年 7 月的一篇文章中](https://msrc-blog.microsoft.com/2019/07/18/we-need-a-safer-systems-programming-language/)表示：“我们认为 Rust 编程语言是目前业界尽可能采用的最佳选择，因为它能够以一种内存安全的方式编写系统级程序。”

随后，他们撰写了博客文章“[为什么用 Rust 进行安全的系统编程](https://msrc-blog.microsoft.com/2019/07/22/why-rust-for-safe-systems-programming/)”，作为 “Rust-Is-Better-than-C++” 系列的一部分，MSRC 团队表示：“Rust 与 C 和 C++ 的区别在于其强大的安全保证。”

![TIOBE Index for Rust ](https://visualstudiomagazine.com/articles/2020/06/02/~/media/ECG/visualstudiomagazine/Images/2020/06/why_rust.asxh)

但是除了性能和安全性以外，MSRC 团队还发现其他 Microsoft 团队出于其他原因而使用 Rust，包括：

- 根据一项内部调查，采纳 Rust 的首要原因是“正确性” —— 这是 Rust 安全保证的延伸，它致力于实现格言“如果编译成功，那么它就能很好地运作”。
- Rust 静态地强行限制许多超越内存安全的属性，包括空指针安全性和数据竞争安全性（即不能从两个或多个线程对一块内存进行非同步访问）。
- 微软的许多团队已经发现，Rust 丰富的类型系统使得编写表达性程序很方便。带关联数据的枚举和强大的 trait 系统等概念进一步强化了 Rust 使程序尽可能无 bug 的目标。
- Rust 现有的社区为该语言带来了巨大的好处。一门语言的强大功能大多来自其核心之外的库、工具链和学习材料。虽然 Rust 仍然是一种年轻的语言，但它已经拥有一个健康的生态系统，拥有一个活跃和开放的编译器与语言开发过程，并且它显示了促进一个强大的开源社区和支持生产用户的能力。这让我们更有理由相信这种语言有一个光明的未来。

MSRC 团队说：“我们相信 Rust 在编写安全系统软件方面会改变游戏规则。Rust 提供编写底层系统所需的性能和控制，同时使软件开发人员能够编写健壮，安全的程序。”

虽然微软还没有正式将其 C++ 代码替换为 Rust，但 MSRC 团队已经开始关注 Rust，撰写各种博文，包括:

- [The Safety Boat: Kubernetes and Rust](https://msrc-blog.microsoft.com/2020/04/29/the-safety-boat-kubernetes-and-rust/)
- [Using Rust in Windows](https://msrc-blog.microsoft.com/2019/11/07/using-rust-in-windows/)
- [An intern's experience with Rust](https://msrc-blog.microsoft.com/2019/10/16/an-interns-experience-with-rust/)
- [Designing a COM library for Rust](https://msrc-blog.microsoft.com/2019/10/08/designing-a-com-library-for-rust/)
- [Building the Azure IoT Edge Security Daemon in Rust](https://msrc-blog.microsoft.com/2019/09/30/building-the-azure-iot-edge-security-daemon-in-rust/)

所以，以 .Net 为中心的开发者们，如果你发现更多来自微软的“ Rust 程序员招聘”帖子，不要感到惊讶。
