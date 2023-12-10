# 1. 问：你为什么写这个

答：恨铁不成钢。

# 2. 问：你是不是对BASIC语言有偏见
答： 不是只有[FreeBASIC](https://freebasic.net/)才是BASIC语言。要论遵守BASIC的原意（你知道BASIC语言名字由来嘛？是Beginner's All-purpose Symbolic Instruction Code，即“初学者通用符号指令代码”的首字母缩写词），我觉得[易语言](https://www.eyuyan.com/)都比[FreeBASIC](https://freebasic.net/)更忠诚。啥？你说这是因为[易语言](https://www.eyuyan.com/)是VB的汉化版？可拉倒吧，去看看编译原理的资料吧
# 3. 问：你觉得[FreeBASIC](https://freebasic.net/)哪里不爽？或者说希望[FreeBASIC](https://freebasic.net/)有哪些新功能/提供哪些库？

答： 按顺序为

- 因为我平时经常处理的数据类型，是字符串，所以BASIC/C这种古董语言的方法（函数名放最前面），写着累、看着也累。希望引入[python](https://www.python.org/)的索引以及（注意，这里是“and”，不是“or”）切片、索引/切片下标支持正数/负数/步长/省略下标/省略步长、函数级联
- 对字符串/数组等，提供 for each，要知道[VB都提供了](https://learn.microsoft.com/en-us/dotnet/visual-basic/language-reference/statements/for-each-next-statement)
- 字符串插值（String Interpolation），要知道[VB都提供了](https://docs.microsoft.com/en-us/dotnet/visual-basic/language-reference/special-characters/interpolated)
- 原生字符串、多行字符串。当然这会让传统BASIC用户不舒服，因为他们很害怕把单引号`'`（传统上用作注释开头的符号）用掉。那就用反引号 \` 呗。不过我个人是喜欢单引号、双引号、三个单引号、三个双引号的字符串；注释嘛，我觉得`#` 蛮好，`//`也不错
- 我平时处理多的，是WORD、EXCEL文件。[FreeBASIC](https://freebasic.net/)则[除了通过COM，几乎没法读写](https://www.freebasic.net/forum/viewtopic.php?p=233645)。啥？土豪你有[LibXL](https://www.libxl.com/)？
- 即便[FreeBASIC](https://freebasic.net/)通过COM读了EXCEL文件，也没有[python](https://www.python.org/)的[pandas](https://pandas.pydata.org/)那样的处理库——当然，这确实有点难为[FreeBASIC](https://freebasic.net/)了，因为没几个语言有这样的库
- 索引/切片不仅适用于字符串，而且适用于其它可索引/迭代对象
- 函数级联操作不仅适用于字符串，而且适用于其它对象。等等，你说我提到了“对象”，而[FreeBASIC](https://freebasic.net/)并不是面向对象的语言？那就使用统一函数调用（Uniform Function Call Syntax ，UFCS）呗；这个特性，D语言、Nim语言等等都提供了
- 对字符串/数组等，提供 `in` 判断元素在不在里面
- Elixir语言的[魔符(Sigil) 字符串](https://elixirschool.com/zh-hans/lessons/basics/sigils)

# 4. 问：你提到的操作，[FreeBASIC](https://freebasic.net/)可以实现效果
答： 你用汇编语言写代码嘛？它也可以达到C、[FreeBASIC](https://freebasic.net/)代码的效果。

# 5. 问：觉得不爽，你咋不去完善[FreeBASIC](https://freebasic.net/)？
答： 

- 我早过了激情燃烧、万事手搓的年龄。作为非IT工作者，工作中需要使用快速、实用、适用、稳定的工具；不可能发现问题，自己还去追踪、分析、查看编译器、库这样的底层
- [FreeBASIC](https://freebasic.net/)官方和部分用户，[不愿意](https://www.freebasic.net/forum/viewtopic.php?p=269714)看到[FreeBASIC](https://freebasic.net/)引入新语法
- 我猜测无法方便地修改[FreeBASIC](https://freebasic.net/)自身的祖传代码，以便支持新语法
- 我认为软件测试、提需求、提bug，也是对软件发展的有益环节。工具/软件/库，越多人用，越可能暴露问题，越可能快速发展；否则永远只是自娱自乐的玩具


# 6. 问：你的提议，破坏了BASIC语言语法的纯洁性！
答：纯洁性？一个字回答的话，那就是“呸”。
详细回答的话，如果引入不兼容的改动，能提供更高开发效率，有何不可？！

要知道[FreeBASIC](https://freebasic.net/)自身都背叛了自己的[初衷：与微软的QuickBASIC兼容](https://www.freebasic.net/wiki/CompilerAbout)。

- 为了变成强大的开发工具，早就提供了传统BASIC不支持的语法。例如

  - 必须声明变量类型

  - [zstring](https://www.freebasic.net/wiki/KeyPgZstring)

  - 使用`!`符号[支持字符串转义](https://www.freebasic.net/wiki/KeyPgOpPpEscape)

  - 使用`[]`符号[进行字符串索引](https://www.freebasic.net/wiki/KeyPgOpStringIndex)

  - 等等、等等改动


- 以及[丢弃了一些关键词](https://www.freebasic.net/wiki/ObsoletedKwds)

总之，若论遵循传统，[FreeBASIC](https://freebasic.net/)已经是一个怪胎了，它背叛了BASIC（你知道BASIC语言名字由来嘛？是Beginner's All-purpose Symbolic Instruction Code，即“初学者通用符号指令代码”的首字母缩写词），试图成为强大的语言时，引入了不少C语言语法习惯。但这个披着BASIC语言外衣的C语言，既没有达到VB的易用性从而吸引新手，也没有在专业的IT圈内吸引太多专业人士。就那么一点用户量，在乎啥破坏性更新？人家Python2到3、Go、zig语言都不怕。

# 7. 问：你觉得[FreeBASIC](https://freebasic.net/)未来会发展到什么程度？
答： 如果不发生奇迹的话，那就是只能用“一如既往”描述。如果非要给这个描述加上一个期限的话，我觉是无限期。

论坛帖子 中 coderJeff 提到1.20版本的开发，他说要[关注开发真的项目](https://www.freebasic.net/forum/viewtopic.php?t=32254)，而不是单纯[FreeBASIC](https://freebasic.net/)自身。不知道这是不是[FreeBASIC](https://freebasic.net/)官方想法。很可惜，[FreeBASIC](https://freebasic.net/)诞生的目的只是为了再生[QuickBASIC](https://www.freebasic.net/wiki/QuickBASIC)；逐步发展出了一些新功能；但是基本长期上踯躅不前。前期错过了开发稍微大一点的项目、提供给用户使用，然后用户找bug、提意见的发展过程。不知现在还能不能迎头赶上。

# 8. 问：你没有觉得[FreeBASIC](https://freebasic.net/)哪里爽？
答： 有两处

- 使用[var声明变量，把类型推断丢给编译器](https://www.freebasic.net/wiki/KeyPgVar)
- 搭配了[MyFbFramework](https://github.com/XusinboyBekchanov/MyFbFramework)的[VisualFBEditor](https://github.com/XusinboyBekchanov/VisualFBEditor)，有点VB那味。当然了，用户少、测试少，还是有bug。近期的[MyFbFramework](https://github.com/XusinboyBekchanov/MyFbFramework)提供了webview2控件，期待可以使用它进行GUI开发；最好多数操作直接[FreeBASIC](https://freebasic.net/)写完，而不借助Javascript。
# 9. 问：我觉得你在找碴
答： 嘴巴、大脑是你的，没人阻止你这样说，请便

