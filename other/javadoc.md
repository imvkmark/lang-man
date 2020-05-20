# man - javadoc(9)

用法:
    javadoc [options] [packagenames] [sourcefiles] [@files]
其中, 选项包括:
    --add-modules <模块>(,<模块>)*
                  除了初始模块之外要解析的根模块;
                  如果 <模块> 为 ALL-MODULE-PATH,
                  则为模块路径中的所有模块。
    -bootclasspath <路径>
                  覆盖用于非模块化发行版的
                  平台类文件的位置
    -breakiterator
                  计算带有 BreakIterator 的第一个语句
    --class-path <路径>, -classpath <路径>, -cp <路径>
                  指定查找用户类文件的位置
    -doclet <类>   通过替代 doclet 生成输出
    -docletpath <路径>
                  指定查找 doclet 类文件的位置
    --enable-preview
                  启用预览语言功能。与 -source 或 --release
                  一起使用。
    -encoding <名称>
                  源文件编码名称
    -exclude <程序包列表>
                  指定要排除的程序包列表
    --expand-requires <值>
                  指示工具展开要文档化的模块集。
                  默认情况下, 将仅文档化命令行中明确
                  指定的模块。值 "transitive" 将额外包含
                  这些模块的所有 "requires transitive"
                  被依赖对象。值 "all" 将包含这些模块
                  的所有被依赖对象。
    -extdirs <目录列表>
                  覆盖所安装扩展的位置
    --help, -help, -?, -h
                  显示命令行选项并退出
    --help-extra, -X
                  输出非标准选项的提要并退出
    -J<标记>        直接将 <标记> 传递给运行时系统
    --limit-modules <模块>(,<模块>)*
                  限制可观察模块的领域
    -locale <名称>  要使用的区域设置, 例如, en_US 或 en_US_WIN
    --module <模块>(,<模块>)*
                  文档化指定模块
    --module-path <路径>, -p <路径>
                  指定查找应用程序模块的位置
    --module-source-path <路径>
                  指定查找多个模块的输入源文件的位置
    -package
                  显示程序包/受保护/公共类型和成员。对于
                  命名模块, 显示所有程序包和所有模块详细信息。
    -private
                  显示所有类型和成员。对于命名模块,
                  显示所有程序包和所有模块详细信息。
    -protected
                  显示受保护/公共类型和成员 (默认设置)。对于
                  命名模块, 显示导出的程序包和模块的 API。
    -public
                  只显示公共类型和成员。对于命名模块,
                  显示导出的程序包和模块的 API。
    -quiet        不显示状态消息
    --release <发行版>
                  提供与指定发行版的源兼容性
    --show-members <值>
                  指定将文档化的成员 (字段, 方法等), 其值可以
                  为 "public", "protected", "package" 或
                  "private" 之一。默认值为 "protected", 该值将
                  显示公共和受保护成员, "public" 将仅显示
                  公共成员, "package" 将显示公共, 受保护和
                  程序包成员, "private" 将显示所有成员。
    --show-module-contents <值>
                  指定模块声明的文档粒度。
                  可能的值为 "api" 或 "all"。
    --show-packages <值>
                  指定将文档化的模块的程序包。
                  可能的值为 "exported" 或 "all" 程序包。
    --show-types <值>
                  指定将文档化的类型 (类, 接口等), 其值可以
                  为 "public", "protected", "package" 或
                  "private" 之一。默认值为 "protected", 该值将
                  显示公共和受保护类型, "public" 将仅显示
                  公共类型, "package" 将显示公共, 受保护和
                  程序包类型, "private" 将显示所有类型。
    --source <发行版>, -source <发行版>
                  提供与指定发行版的源兼容性
    --source-path <路径>, -sourcepath <路径>
                  指定查找源文件的位置
    -subpackages <子程序包列表>
                  指定要递归加载的子程序包
    --system <jdk>
                  覆盖用于模块化发行版的系统模块的位置
    --upgrade-module-path <路径>
                  覆盖可升级模块位置
    -verbose      输出有关 Javadoc 正在执行的操作的消息
    --version     输出版本信息

由 Standard doclet 提供:
    --add-stylesheet <file>
                  用于所生成文档的其他样式表文件
    --allow-script-in-comments
                  允许在选项和注释中使用 JavaScript
    -author       包含 @author 段
    -bottom <html-code>
                  包含每个页面的底部文本
    -charset <charset>
                  用于跨平台查看生成的文档的字符集
    -d <directory>
                  输出文件的目标目录
    -docencoding <name>
                  指定输出的字符编码
    -docfilessubdirs
                  递归复制文档文件子目录
    -doctitle <html-code>
                  包含概览页面的标题
    -excludedocfilessubdir <name>:..
                  排除具有给定名称的所有文档文件子目录
    -footer <html-code>
                  包含每个页面的页脚文本
    -group <name> <g1>:<g2>...
                  将指定的元素在概览页面上分组在一起
    -header <html-code>
                  包含每个页面的页眉文本
    -helpfile <file>
                  包含帮助链接所链接到的文件
    -html5        生成 HTML 5 输出。此选项不再是必需的。
    --javafx, -javafx
                  启用 JavaFX 功能
    -keywords     随程序包, 类和成员信息一起附带 HTML 元标记
    -link <url>   创建指向 <url> 中的 javadoc 输出的链接
    -linkoffline <url1> <url2>
                  使用 <url2> 中的程序包列表链接到 <url1> 中的文档
    -linksource   以 HTML 格式生成源文件
    --main-stylesheet <file>, -stylesheetfile <file>
                  用于更改生成文档的样式的文件
    -nocomment    不生成说明和标记, 只生成声明
    -nodeprecated
                  不包含 @deprecated 信息
    -nodeprecatedlist
                  不生成已过时的列表
    -nohelp       不生成帮助链接
    -noindex      不生成索引
    -nonavbar     不生成导航栏
    -noqualifier <name1>:<name2>:..
                  输出中不包括限定符的列表
    -nosince      不包括 @since 信息
    -notimestamp  不包括隐藏的时间戳
    -notree       不生成类分层结构
    --override-methods (detail|summary)
                  在详细资料部分或概要部分中的文档覆盖方法
    -overview <file>
                  从 HTML 文件读取概览文档
    -serialwarn   生成有关 @serial 标记的警告
    -sourcetab <tab length>
                  指定源中每个制表符占据的空格数
    -splitindex   将索引分为每个字母对应一个文件
    -tag <name>:<locations>:<header>
                  指定单个参数定制标记
    -taglet       要注册的 Taglet 的全限定名称
    -tagletpath   Taglet 的路径
    -top <html-code>
                  包含每个页面的顶部文本
    -use          创建类和程序包用法页面
    -version      包含 @version 段
    -windowtitle <text>
                  文档的浏览器窗口标题

GNU 样式的选项可使用 = (而非空白) 来分隔选项名称
及其值。