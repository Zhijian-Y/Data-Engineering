\mainmatter

# 文学式编程{#md}

可复现性是数据工程誓死捍卫的底线原则与科学研究区分于巫术的主要特征。R语言内嵌了一整套自动化报告解决方案，可以保证结果可复现。另一方面，任何数据分析报告都不是一簇而就的，必然涉及到反反复复的结果调试，R语言自动化报告可以帮我们避免反复将分析结果赋值粘贴到Word文档里面（如果你不理解这句话，那说明你还不是一个资深数据分析人员），避免了这种愚蠢的重复劳动。我们一直认为懒没有错，因为懒是推动人类寻找更高效技术方案的原生动力，自动化报告就是这样的技术方案。

## 什么是文学式编程

文学式编程是相对于结构式编程而言的。结构式编程就是我们前面学到的那些循环、分支结构、函数等代码，让计算机按照我们的设定去执行特定任务。但是在展示这些运算结果的时候，我们还需要将其编辑到一个文档或者演示文稿中。文学式编程则是将这两步融合在一起，分析报告的正文和代码放入同一个文档，编译的时候分别运行，从而一次性生成分析报告。

文学式编程起源于大神Knuth开发的Sweave框架，大名鼎鼎的Tex就是其作品。写到这里，忍不住要提到Tex开发的故事，当年Knuth老人家不满出版社的排版质量，一气之下写了一套高质量排版系统，并写支票奖励发现缺陷的人，奖金都是16进制的1美元，而且金额随缺陷数目递增（这段轶事大神谢益辉的书籍中也有记载）。

2011年，R语言社区大神谢益辉（我在课上把他称为华人之光）由于忍不了Sweave的图片宽度设置等问题，一气之下（又来！）开发了knitr包（具体这段历史可以参考谢益辉自己的[回忆](https://bookdown.org/yihui/r-ninja/auto-report.html)^[R语言忍者秘笈 https://bookdown.org/yihui/r-ninja/ ]），兼容并无限拓展Sweave，把我们从LaTex的深坑中拯救了出来。读到这里，如果你还没有体会过LaTex的坑有多深，那么恭喜你，你可以不用体会，直接跳入RMarkdown的简洁世界吧。

上面的故事也告诉我们，如果你想推动技术进步，就让程序员生气吧，忍无可忍的程序员总会搞出一些惊天动地的事情。

## 文学式编程的应用
