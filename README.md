## git-dir & work-tree ##

如果想將 pygit2 repository 中的某些 commit copy 到 D:\pygit2 以外的目錄中。此時可以考慮使用 git checkout 或者 git reset 命令來實現，只需顯式指定 `working-tree` 即可。

`假定想將 D:\pygit2 中的 master copy 到 D:\bak 中`

方法一

	1.1 git --git-dir=D:\\pygit2\\.git --work-tree=D:\\bak status
	此時可以看到很多提示信息，意思是 D:\\bak 和 D:\pygit2 repository 相比很多文件缺失
	
	1.2 git --git-dir=D:\\pygit2\\.git --work-tree=D:\\bak checkout -b tmp -f master
	使用 `-f` 強制 checkout，並創建一個 tmp 的 branch
	
	1.3 git --git-dir=D:\\pygit2\\.git --work-tree=D:\\bak  branch -d tmp
	刪除tmp branch
	
	1.4 此時可以看到 D:\\bak 中的內容已經被更新為 D:\\pygit2\\.git master branch 的內容

方法二

	2.1 git --git-dir=D:\\pygit2\\.git --work-tree=D:\\bak reset --quiet --hard
	2.2 此時可以看到 D:\\bak 中的內容已經被更新為 D:\\pygit2\\.git master branch 的內容，不過這種方法存在一定的弊端，
　　　　　　那就是 index 中的內容都已經丟失，想要恢復的話存在一定的難度，所以在使用 reset 之前還是慎重一些比較好。

[Git系列之二 --- git-dir & work-tree](http://www.cnblogs.com/Jerryshome/archive/2011/12/15/2289218.html)
