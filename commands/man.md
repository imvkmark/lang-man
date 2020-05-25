# man - man(1)

系统手册的帮助文档查看工具, 通过man指令可以查看Linux中的指令帮助、配置文件帮助和编程帮助等信息。


```
man [-acdfFhkKtwW] [--path] [-m system] [-p string] [-C config_file] [-M pathlist] [-P pager] [-B browser] [-H htmlpager] [-S section_list] [section] name ...
```

## 说明

`man` formats and displays the on-line manual pages. If you specify *section*, `man` only looks in that section of the manual. *name* is normally the name of the manual page, which is typically the name of a command, function, or file. However, if *name* contains a slash (`/`) then `man` interprets it as a file specification, so that you can do `man ./foo.5` or even `man /cd/foo/bar.1.gz`.
See below for a description of where `man` looks for the manual page files.

## 示例

我们输入`man ls`，它会在最左上角显示“LS（1）”，在这里，“LS”表示手册名称，而“（1）”表示该手册位于第一节章，同样，我们输`man ifconfig`它会在最左上角显示“IFCONFIG（8）”。也可以这样输入命令：“man [章节号] 手册名称”。

man是按照手册的章节号的顺序进行搜索的，比如：

```
man sleep
```

只会显示sleep命令的手册,如果想查看库函数sleep，就要输入:

```
man 3 sleep
```

### 手册部分说明

手册的标准部分包括:
`1`  : 用户命令
`2`  : 系统调用
`3`  : C库函数
`4` : 设备和特殊文件
`5` : 文件格式和约定
`6` : 游戏等。。
`7` : 杂集
`8` : 系统管理工具和deamons发行版根据它们的具体情况定制的手册部分，其中通常包括其他部分。


## 选项

`-C config_file`
Specify the configuration file to use; the default is `/etc/man.config`. (See `[man.config](https://linux.die.net/man/5/man.config)`(5).)

`-M path`
指定另外的 man 文件路径来进行搜索 `path` 字串使用冒号分隔路径, 默认 `man` 使用 `manpath` 命令输出的路径来进行搜索.空列表与完全不指定路径结果一致

`-P pager`
指定使用哪种分页程序, 这个选项覆盖 `MANPAGER` 环境变量, 同时 `MANPAGER` 又覆盖了 `PAGER` 变量,   默认 `man` 使用 `less`, `/usr/bin/less -is`, 如果 `less` 不存在或者不可执行, 则会使用 `cat`.

`-B`
Specify which browser to use on HTML files. This option overrides the `BROWSER` environment variable. By default, `man` uses `/usr/bin/less`-is`,`

`-H`
Specify a command that renders HTML files as text. This option overrides the `HTMLPAGER` environment variable. By default, `man` uses `/bin/cat`,
`-S section_list`
List is a colon separated list of manual sections to search. This option overrides the `MANSECT` environment variable.

`-a`
默认, `man` 将在它找到的最合适的页面并显示后退出。使用此选项将强制 `man` 显示所有具有与搜索条件匹配的名称的手册页。

`-c`
Reformat the source man page, even when an up-to-date cat page exists. This can be meaningful if the cat page was formatted for a screen with a different number of columns, or if the preformatted page is corrupted.

`-d`
Don't actually display the man pages, but do print gobs of debugging information.

`-D`
Both display and print debugging info.

`-f`
等同于 `whatis`.

`-F` or `--preformat`
Format only - do not display.

`-h`
Print a help message and exit.

`-k`
Equivalent to `apropos`.

`-K`
Search for the specified string in *all* man pages. Warning: this is probably very slow! It helps to specify a section. (Just to give a rough idea, on my machine this takes about a minute per 500 man pages.)

`-m system`
Specify an alternate set of man pages to search based on the system name given.

`-p string`
Specify the sequence of preprocessors to run before `nroff` or `troff`. Not all installations will have a full set of preprocessors. Some of the preprocessors and the letters used to designate them are: eqn (e), grap (g), pic (p), tbl (t), vgrind (v), refer (r). This option overrides the `MANROFFSEQ` environment variable.

`-t`
Use `/usr/bin/groff -Tps -mandoc` to format the manual page, passing the output to `stdout.` The default output format of `/usr/bin/groff -Tps -mandoc` is Postscript, refer to the manual page of `/usr/bin/groff -Tps -mandoc` for ways to pick an alternate format.
Depending on the selected format and the availability of printing devices, the output may need to be passed through some filter or another before being printed.

`-w` or `--path`
Don't actually display the man pages, but do print the `location`(s) of the files that would be formatted or displayed. If no argument is given: display (on stdout) the list of directories that is searched by `man` for man pages. If `manpath` is a link to man, then "manpath" is equivalent to "man --path".

`-W`
Like -w, but print file names one per line, without additional information. This is useful in shell commands like `man -aW man | xargs ls -l`

## Cat Pages

Man will try to save the formatted man pages, in order to save formatting time the next time these pages are needed. Traditionally, formatted versions of pages in DIR/manX are saved in DIR/catX, but other mappings from man dir to cat dir can be specified in `/etc/man.config`. No cat pages are saved when the required cat directory does not exist. No cat pages are saved when they are formatted for a line length different from 80\. No cat pages are saved when man.config contains the line NOCACHE.
It is possible to make `man` suid to a user man. Then, if a cat directory has owner man and mode 0755 (only writable by man), and the cat files have owner man and mode 0644 or 0444 (only writable by man, or not writable at all), no ordinary user can change the cat pages or put other files in the cat directory. If `man` is not made suid, then a cat directory should have mode 0777 if all users should be able to leave cat pages there.
The option `-c` forces reformatting a page, even if a recent cat page exists.

## Html 页面
Man will find HTML pages if they live in directories named as expected to be ".html", thus a valid name for an HTML version of the `[ls](https://linux.die.net/man/1/ls)`(1) man page would be */usr/share/man/htmlman1/ls.1.html*.

## Search Path For Manual Pages

`man` uses a sophisticated method of finding manual page files, based on the invocation options and environment variables, the `/etc/man.config` configuration file, and some built in conventions and heuristics.
First of all, when the *name* argument to `man` contains a slash (`/`), `man` assumes it is a file specification itself, and there is no searching involved.
But in the normal case where *name* doesn't contain a slash, `man` searches a variety of directories for a file that could be a manual page for the topic named.
If you specify the `-M pathlist` option, *pathlist* is a colon-separated list of the directories that `man` searches.
If you don't specify `-M` but set the `MANPATH` environment variable, the value of that variable is the list of the directories that `man` searches.
If you don't specify an explicit path list with `-M` or `MANPATH, man` develops its own path list based on the contents of the configuration file `/etc/man.config`. The `MANPATH` statements in the configuration file identify particular directories to include in the search path.
Furthermore, the `MANPATH_MAP` statements add to the search path depending on your command search path (i.e. your `PATH` environment variable). For each directory that may be in the command search path, a `MANPATH_MAP` statement specifies a directory that should be added to the search path for manual page files. `man` looks at the `PATH` variable and adds the corresponding directories to the manual page file search path. Thus, with the proper use of `MANPATH_MAP`, when you issue the command `man xyz`, you get a manual page for the program that would run if you issued the command `xyz`.
In addition, for each directory in the command search path (we'll call it a "command directory") for which you do *not* have a `MANPATH_MAP` statement, `man` automatically looks for a manual page directory "nearby" namely as a subdirectory in the command directory itself or in the parent directory of the command directory.
You can disable the automatic "nearby" searches by including a `NOAUTOPATH` statement in `/etc/man.config`.
In each directory in the search path as described above, `man` searches for a file named *topic.section*, with an optional suffix on the section number and possibly a compression suffix. If it doesn't find such a file, it then looks in any subdirectories named `manN` or `catN` where *N* is the manual section number. If the file is in a `catN` subdirectory, `man` assumes it is a formatted manual page file (cat page). Otherwise, `man` assumes it is unformatted. In either case, if the filename has a known compression suffix (like `.gz`), `man` assumes it is gzipped.
If you want to see where (or if) `man` would find the manual page for a particular topic, use the `--path` (`-w`) option.

## 环境变量

`MANPATH`
If `MANPATH` is set, `man` uses it as the path to search for manual page files. It overrides the configuration file and the automatic search path, but is overridden by the `-M` invocation option. See `SEARCH PATH FOR MANUAL PAGES`.

`MANPL`
If `MANPL` is set, its value is used as the display page length. Otherwise, the entire man page will occupy one (long) page.

`MANROFFSEQ`
If `MANROFFSEQ` is set, its value is used to determine the set of preprocessors run before running `nroff` or `troff`. By default, pages are passed through the tbl preprocessor before `nroff`.

`MANSECT`
If `MANSECT` is set, its value is used to determine which manual sections to search.

`MANWIDTH`
If `MANWIDTH` is set, its value is used as the width manpages should be displayed. Otherwise the pages may be displayed over the whole width of your screen.

`MANPAGER`
If `MANPAGER` is set, its value is used as the name of the program to use to display the man page. If not, then `PAGER` is used. If that has no value either, `/usr/bin/less -is` is used.

`BROWSER`
The name of a browser to use for displaying HTML manual pages. If it is not set, /usr/bin/less -is is used.

`HTMLPAGER`
The command to use for rendering HTML manual pages as text. If it is not set, /bin/cat is used.

`LANG`
If `LANG` is set, its value defines the name of the subdirectory where man first looks for man pages. Thus, the command 'LANG=dk man 1 foo' will cause man to look for the foo man page in .../dk/man1/foo.1, and if it cannot find such a file, then in .../man1/foo.1, where ... is a directory on the search path.

`NLSPATH, LC_MESSAGES, LANG`
The environment variables `NLSPATH` and `LC_MESSAGES` (or `LANG` when the latter does not exist) play a role in locating the message catalog. (But the English messages are compiled in, and for English no catalog is required.) Note that programs like ``[col](https://linux.die.net/man/1/col)`(1)` called by man also use e.g. LC_CTYPE.

`PATH`

`PATH` helps determine the search path for manual page files. See `SEARCH PATH FOR MANUAL PAGES`.

`SYSTEM`

`SYSTEM` is used to get the default alternate system name (for use with the `-m` option).


