# 插件使用

## 【独立运行插件使用方法】
1. 右键RunAny图标“插件管理”，下载独立运行插件,如`huiZz_MButton.ahk`、`huiZz_InputEnCn.ahk`  
2. 下载后点击“启动”按钮即可使用，点击“编辑”按钮可以阅读说明和进行配置  
3. 在插件管理点击“自启”按钮设置huiZz_MButton.ahk为随RunAny而自动启动  

---

## 【ObjReg插件使用方法】
以下插件配置需要同时下载`ObjReg插件对象注册工具（不用自启）`

![RunAny插件设置自动启动](/assets/images/RunAny插件设置自动启动.png)

### huiZz_QRCode二维码脚本使用方法
1. 右键RunAny图标“插件管理”，下载插件huiZz_QRCode.ahk和RunAny_ObjReg.ahk  
2. 下载后在插件管理点击“自启”按钮设置huiZz_QRCode.ahk为自动启动  
3. 复制以下执行项写入`RunAny.ini`文件保存，然后重启RunAny后打开菜单即可使用  

```autohotkey
二维码生成|huiZz_QRCode[qr_code](%getZz%)
```


### huiZz_Window窗口操作插件使用方法
1. 右键RunAny图标“插件管理”，下载插件huizz_Window.ahk和RunAny_ObjReg.ahk  
2. 下载后在插件管理点击“自启”按钮设置huizz_Window.ahk为自动启动  
3. 复制以下执行项写入`RunAny.ini`文件保存，然后重启RunAny后打开菜单即可使用  

<details>
<summary>【点击展开】复制需要的功能写入RunAny.ini文件</summary>

<PRE>
;使用左Win键搭配鼠标右键或滚轮的使用方式
窗口居中&#9LWin & RButton|huiZz_Window[win_center_zz]()
窗口透明化&#9LWin & WheelDown|huiZz_Window[win_transparency_zz](1,30)
窗口不透明&#9LWin & WheelUp|huiZz_Window[win_transparency_zz](0,30)
</PRE>

```autohotkey
-窗口函数
	;外接ahk脚本名[函数名](函数传参数，可以无参)
	窗口居中|huiZz_Window[win_center_zz]()
	窗口置顶|huiZz_Window[win_top_zz](1)
	窗口取消置顶|huiZz_Window[win_top_zz](0)
	窗口置顶时透明|huiZz_Window[win_transparent_top_zz]()
	--
	窗口透明化|huiZz_Window[win_transparency_zz](1,20)
	窗口不透明|huiZz_Window[win_transparency_zz](0,20)
	窗口最大化显示|huiZz_Window[win_max_zz]()
	--
	窗口改变大小并移动|huiZz_Window[win_move_size_zz](0,0,800,600)
	;外接函数参数明确数值的情况(速度最快，推荐)
	窗口340x200|huiZz_Window[win_size_zz](340,200)
	窗口650x384|huiZz_Window[win_size_zz](650,384)
	窗口800x600|huiZz_Window[win_size_zz](800,600)
	窗口1024x768|huiZz_Window[win_size_zz](1024,768)
	;外接函数参数需要用到系统环境变量(适用不同电脑情况，速度快)
	窗口竖半屏|huiZz_Window[win_size_zz](960,%A_ScreenHeight%)
	;外接函数参数为动态表达式计算值(适用复杂函数情况，在()前加%区分，速度慢)
	窗口占比0.5x0.5|huiZz_Window[win_size_zz]%(A_ScreenWidth*0.5,A_ScreenHeight*0.5)
	窗口占比0.8x0.8|huiZz_Window[win_size_zz]%(A_ScreenWidth*0.8,A_ScreenHeight*0.8)
	窗口占比0.8x0.9|huiZz_Window[win_size_zz]%(A_ScreenWidth*0.8,A_ScreenHeight*0.9)
	--
	;窗口移至边角置顶观影[win_movie_zz](mode=1,x=0,y=0,title=0)
	;参数说明：
	;mode：1-左上,2-右上,3-左下,4-右下
	;x：正数向左偏移像素，负数向右偏移像素
	;y：正数向下偏移像素，负数向上偏移像素
	;title：0-显示标题栏，1-隐藏标题栏
	屏幕左上角|huiZz_Window[win_movie_zz](1,-10)
	屏幕右上角|huiZz_Window[win_movie_zz](2,10)
	屏幕左下角|huiZz_Window[win_movie_zz](3,-10,10)
	屏幕右下角|huiZz_Window[win_movie_zz](4,10,10)
```

</details>

### huiZz_System系统操作插件使用方法
1. 右键RunAny图标“插件管理”，下载插件huiZz_System.ahk和RunAny_ObjReg.ahk  
2. 下载后在插件管理点击“自启”按钮设置huiZz_System.ahk为自动启动  
3. 复制以下执行项写入`RunAny.ini`文件保存，然后重启RunAny后打开菜单即可使用  

<details>
<summary>【系统函数】</summary>

```autohotkey

-系统函数
	;[获取本地IP][system_ip_zz](output=0)
	;参数说明：output：1-输出IP；0-显示IP并复制到剪贴板
	ip地址|huiZz_System[system_ip_zz]()

	;[定位注册表路径][system_regedit_zz](getZz:="")
	;参数说明：getZz：选中的文本内容
	注册表定位|huiZz_System[system_regedit_zz](%getZz%)

	;[ping选中地址][system_ping_zz](getZz:="")
	;参数说明：getZz：选中的文本内容
	ping|huiZz_System[system_ping_zz](%getZz%)

	;[重启桌面]
	重启桌面|huiZz_System[system_explorer_zz]()
	--
	;[显示系统隐藏文件][system_hidefile_zz](hide=0,sys=0,ext=0,refresh=1)
	;参数说明：
	;hide：0-隐藏文件；1-显示隐藏文件
	;sys：0-隐藏系统文件；1-显示系统文件
	;ext：1-隐藏文件后缀；0-显示文件后缀
	;refresh：1-自动刷新生效；0-手动刷新
	显示隐藏文件|huiZz_System[system_hidefile_zz](1,0,0)
	显示所有文件|huiZz_System[system_hidefile_zz](1,1,0)
	隐藏所有文件|huiZz_System[system_hidefile_zz](0,0,0)
	隐藏文件后缀|huiZz_System[system_hidefile_zz](0,0,1)
```

</details>

<br>

<details>
<summary>【复制路径】</summary>

```autohotkey
--复制路径
	;复制文件说明：path路径, name名称, dir目录, ext后缀, nameNoExt无后缀名称, drive盘符
	;复制快捷方式说明：lnkTarget指向路径, lnkDir指向目录, lnkArgs参数, lnkDesc注释, lnkIcon图标文件名, lnkIconNum图标编号, lnkRunState初始运行方式
	复制名称|huiZz_System[system_file_path_zz](%getZz%,name)
	复制路径|huiZz_System[system_file_path_zz](%getZz%,path)
	复制所在目录|huiZz_System[system_file_path_zz](%getZz%,dir)
	复制无后缀名称|huiZz_System[system_file_path_zz](%getZz%,nameNoExt)
	复制lnk指向路径|huiZz_System[system_file_path_zz](%getZz%,lnkTarget)
	复制lnk指向目录|huiZz_System[system_file_path_zz](%getZz%,lnkDir)

	;[创建目标快捷方式]  
	;参数说明：getZz：选中的文件路径  
	;target：需要发送的目标路径,默认当前目录  
	;lnk：快捷方式名,默认是选中文件名  
	创建快捷方式到桌面|huiZz_System[system_create_shortcut](%getZz%,%A_Desktop%)
```

</details>

### huiZz_Text文本操作插件使用方法
1. 右键RunAny图标“插件管理”，下载插件huizz_Text.ahk和RunAny_ObjReg.ahk  
2. 下载后在插件管理点击“自启”按钮设置huizz_Text.ahk为自动启动  
3. 复制以下执行项写入`RunAny.ini`文件保存，然后重启RunAny后打开菜单即可使用  

<details>
<summary>【文本编辑】</summary>

```autohotkey
-文本函数
	;[文本格式化][text_format_zz](getZz:="",formatStr:="")
	;参数说明：
	;getZz：选中的文本内容
	;formatStr：格式化选项，详情查看(https://wyagd001.github.io/zh-cn/docs/commands/Format.htm)
	转大写|huiZz_Text[text_format_zz](%getZz%,{:U})
	转小写|huiZz_Text[text_format_zz](%getZz%,{:L})
	首字母大写|huiZz_Text[text_format_zz](%getZz%,{:T})
	两位小数|huiZz_Text[text_format_zz](%getZz%,{:0.2f})
	转整数|huiZz_Text[text_format_zz](%getZz%,{:i})
	--
	;[文本替换][text_replace_zz](getZz:="",searchStr:="",replaceStr:="")
	;参数说明：
	;getZz：选中的文本内容
	;searchStr：查找的文本内容
	;replaceStr：用来替换查找到的文本
	替换逗号为空格|huiZz_Text[text_replace_zz](%getZz%,`,,%A_Space%)
	替换逗号为换行|huiZz_Text[text_replace_zz](%getZz%,`,,`n)
	替换空格为换行|huiZz_Text[text_replace_zz](%getZz%, ,`n)
	替换分号为换行|huiZz_Text[text_replace_zz](%getZz%,`;,`n)
	去除空格|huiZz_Text[text_replace_zz](%getZz%,%A_Space%)
	;[文本删除重复行保留顺序]
	;参数说明：getZz：选中的文本内容
	删除重复行保留顺序|huiZz_Text[text_remove_repeat](%getZz%)
	--
	;[文本多行合并][text_merge_zz](getZz:="",splitStr:=" ")
	;参数说明：
	;getZz：选中的文本内容
	;splitStr：换行符替换的分隔文本(默认空格，逗号为特殊字符，转义写成`,)
	多行合并空格分隔|huiZz_Text[text_merge_zz](%getZz%)
	多行合并逗号分隔|huiZz_Text[text_merge_zz](%getZz%,`,)
	--
	;[选中文字编辑]text_edit_zz(getZz:="",editApp:="")
	;参数说明：getZz：选中的文本内容
	;editApp：编辑器软件
	选中文字编辑(&E)|huiZz_Text[text_edit_zz](%getZz%,%"notepad.exe"%)
	选中Sublime编辑(&S)|huiZz_Text[text_edit_zz](%getZz%,%"sublime_text.exe"%)
	;[选中文本比较剪贴板][text_compare_zz](getZz:="",compareApp:="")
	;参数说明：getZz：选中的文本内容
	;compareApp：文本对比软件
	选中文本比较剪贴板|huiZz_Text[text_compare_zz](%getZz%,%"BCompare.exe"%)
	;[便捷运行磁力链接]text_magnet_zz(getZz:="",downApp:="")
	;参数说明：getZz：选中的文本内容
	;downApp：磁链下载软件
	磁力链接|huiZz_Text[text_magnet_zz](%getZz%)
	选中内容与剪贴板互换|huiZz_Text[text_paste_zz](%getZz%)
```

</details>

<br>

<details>
<summary>【排序函数】</summary>

```autohotkey
-排序函数
	;[文本排序][text_sort_zz](getZz:="",options:="")
	;参数说明：
	;getZz：选中的文本内容
	;options：排序选项，详情查看(https://wyagd001.github.io/zh-cn/docs/commands/Sort.htm)
	排序不区分大小写|huiZz_Text[text_sort_zz](%getZz%)
	排序区分大小写|huiZz_Text[text_sort_zz](%getZz%,C)
	排序数字|huiZz_Text[text_sort_zz](%getZz%,N)
	排序逆向|huiZz_Text[text_sort_zz](%getZz%,R)
	排序随机|huiZz_Text[text_sort_zz](%getZz%,Random)
	排序路径最后文件名|huiZz_Text[text_sort_zz](%getZz%,\)
	--
	排序去重不区分大小写|huiZz_Text[text_sort_zz](%getZz%,U)
	排序去重区分大小写|huiZz_Text[text_sort_zz](%getZz%,U C)
	--
	排序逗号分隔|huiZz_Text[text_sort_zz](%getZz%,D`,)
	排序空格分隔|huiZz_Text[text_sort_zz](%getZz%,D )
```

</details>

<br>

<details>
<summary>【变量命名】</summary>

```autohotkey
-变量命名
	;[变量命名][text_var_name_zz](getZz:="",varStr:="",formatStr:="",splitStr:=" ,._-|")
	;参数说明：getZz：选中的文本内容
	;varStr：变量命名格式符号
	;formatStr：格式化选项，详情查看(https://wyagd001.github.io/zh-cn/docs/commands/Format.htm)
	;splitStr：分割用的字符，一般不用传使用默认值 ,._-|
	1骆驼命名(camelCase)|huiZz_Text[text_var_name_zz](%getZz%,,{1:L}{:T})
	2帕斯卡命名(PascalCase)|huiZz_Text[text_var_name_zz](%getZz%,,{:T})
	3下划线命名(snake_case)|huiZz_Text[text_var_name_zz](%getZz%,_,{:L})
	4横杠命名(kebab-case)|huiZz_Text[text_var_name_zz](%getZz%,-,{:L})
	5常量命名(SCREAMING_SNAKE_CASE)|huiZz_Text[text_var_name_zz](%getZz%,_,{:U})
	6包名命名(dot.case)|huiZz_Text[text_var_name_zz](%getZz%,.,{:L})
	7空格命名(camel case)|huiZz_Text[text_var_name_zz](%getZz%, ,{:L})
	8网络路径命名(dot/case)|huiZz_Text[text_var_name_zz](%getZz%,`/,{:L})
	9文件路径命名(dot\case)|huiZz_Text[text_var_name_zz](%getZz%,`\,{:L})
```

</details>

<br>

<details>
<summary>【Markdown】</summary>

```autohotkey
-Markdown	!m
	;[Markdown格式化][text_format_md_zz](getZz:="",formatStr:="")
	;参数说明：getZz：选中的文本内容
	;formatStr：格式化选项，详情查看(https://wyagd001.github.io/zh-cn/docs/commands/Format.htm)
	1标题#|huiZz_Text[text_format_md_zz](%getZz%,# {1})
	2标题##|huiZz_Text[text_format_md_zz](%getZz%,## {1})
	3标题###|huiZz_Text[text_format_md_zz](%getZz%,### {1})
	**加粗**|huiZz_Text[text_format_md_zz](%getZz%,**{1}**)
	*斜体*|huiZz_Text[text_format_md_zz](%getZz%,*{1}*)
	***斜体加粗***|huiZz_Text[text_format_md_zz](%getZz%,***{1}***)
	`代码行`|huiZz_Text[text_format_md_zz](%getZz%,``{1}``)
	<u>下划线</u>|huiZz_Text[text_format_md_zz](%getZz%,<u>{1}</u>)
	~~删除线~~|huiZz_Text[text_format_md_zz](%getZz%,~~{1}~~)
	--
	;[批量添加序号][text_seq_num_zz](getZz:="",seqNumStr:="",arab:=1)
	;参数说明：getZz：选中的文本内容
	;arab：0-中文数字；1-阿拉伯数字
	;seqNumStr：序号形式
	数字序号|huiZz_Text[text_seq_num_zz](%getZz%,. )
	中文序号|huiZz_Text[text_seq_num_zz](%getZz%,、,0)
	转中文数字|huiZz_Text[text_cn2_zz](%getZz%,1)
	转阿拉伯数字|huiZz_Text[text_cn2_zz](%getZz%,0)
	--
	>引用|huiZz_Text[text_format_md_zz](%getZz%,> {1})
	无序列表*|huiZz_Text[text_format_md_zz](%getZz%,* {1})
	无序列表+|huiZz_Text[text_format_md_zz](%getZz%,+ {1})
	无序列表-|huiZz_Text[text_format_md_zz](%getZz%,- {1})
	待办列表|huiZz_Text[text_format_md_zz](%getZz%,- [ ] {1})
	完成列表|huiZz_Text[text_replace_zz](%getZz%,- [ ],- [x])
```

</details>


---

## [新建自定义ObjReg插件]

1. 右键RunAny图标 - 打开“插件管理”
2. 点击右上角“新建插件”按钮，命名后确认创建
3. RunAny会自动设置启用插件，在`class RunAnyObj{}`大括号中编写自己的函数
4. 写好函数后保存脚本，打开``RunAny.ini``按格式把自己的函数放入RunAny菜单
   - `菜单项名|你的脚本文件名RunAny_NewObjReg_1[你的函数名](参数1,参数2)`
5. 保存``RunAny.ini``，重启RunAny后打开菜单测试使用刚刚写的函数功能。

![ObjReg新建插件脚本](/assets/images/ObjReg新建插件脚本.png)