# easyfun.github.io

###github写博客
###Windows环境搭建
    1.安装Sublime Text 3
    2.设置Sublime Text，Tab保存为4个空格
    菜单栏Preferences->Settings - User，在配置文件中增加以下设置
        //把 tab 转换成4个空格
        "tab_size": 4,
        //把tab 转换成 空格
        "translate_tabs_to_spaces": true,
        //关于下行说明, 若不存在, 请手动添加. 若要在保存时自动把tab 转换成空格，请把值设置成 true，如不需要: 设置成 false
        "expand_tabs_on_save": true,
        //此行的主要作用是, 当某行为空格且无其它字符时, 保存时会去除空白
        "trim_trailing_white_space_on_save": true
    3.安装python
    4.安装pelican python模块: pip install pelican
    5.安装markdown python模块: pip install markdown
    6.安装make工具（已集成，见根目录下make.exe）

###生成博客文件
	脚本文件：run.bat/run.sh
	命令：make html

###提交到github
    make github

###markdown教程
    http://www.markdown.cn/
    http://wowubuntu.com/markdown/