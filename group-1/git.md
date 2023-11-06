# GIT

## rebase

用於調整 commit 順序、替換 commit 訊息、整合多個 commit 為一個 commit 。

<pre class="language-git"><code class="lang-git">git log --oneline 

// result
3aeab2b (HEAD -> main) asd
<strong>14d7d2b 1ddd
</strong>3d6541b (origin/main) [feat]: edit table
aa06fb4 [feat]: add Antd
4cca94a first commit
</code></pre>

我們要對 \[feat]: edit table 以上的 commit 做異動的話，基底選用 "add Antd" 的 commit。

```
git rebase -i aa06fb4 
```

就會跳到 vim 介面，最上面是我們可異動的 commit

下面有提供可操作的指令

```
pick 3d6541b [feat]: edit table
pick 14d7d2b 1ddd
pick 3aeab2b asd

# 重定基底 aa06fb4..d6020b9 到 aa06fb4（3 個提交）
#
# 命令：
# p, pick <提交> = 使用提交
# r, reword <提交> = 使用提交，但編輯提交說明
# e, edit <提交> = 使用提交，但不直接修補 (amend)
# s, squash <提交> = 使用提交，但融合至上個提交
# f, fixup [-C | -c] <提交> = 跟 “squash” 相似，但除非傳入 -C，
#                    否則只保留上一個提交的日誌訊息。傳入 -C 表示只保留這個
#                    提交的訊息；傳入 -c 與 -C 功能相同，但會開啟編輯器
# x, exec <命令> = 使用 shell 執行命令（這一列的剩餘部分）
# b, break = 在此停止（使用 “git rebase --continue” 繼續重定基底）
# d, drop <提交> = 移除提交
# l, label <標籤> = 為目前 HEAD 打上指定名字標籤
# t, reset <標籤> = 重設 HEAD 到指定標籤
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
#         建立一個合併提交，並使用原始的合併提交說明（如果沒有指定
#         原始提交，則使用 <oneline> 作為提交說明）。
#         使用 -c <commit> 編輯提交說明。
# u, update-ref <ref> = 為 <ref> 引用設立佔位符號，
#                       以將這個引用更新為此處的新提交。
```

這次我們來合併多個 commit，將三個 commit 合到 3d6541b 的 commit 中

```
pick 3d6541b [feat]: edit table
squash 14d7d2b 1ddd
squash 3aeab2b asd
```

#### 接下來會跳出調整 commit 訊息的 vim

```
# 這是整合 3 個提交的集合提交。
# 這是第一個提交說明：

[feat]: edit table

# 這是提交說明 #2：

1ddd

# 這是提交說明 #3：

asd

# 請輸入描述您變更的提交訊息。開頭是「#」
# 的行皆會忽略。提交訊息空白則取消本次提交作業。
#
# 日期：  Sun Nov 5 22:19:21 2023 +0530
#
# 互動式重定基底動作正在進行中；至 aa06fb4
# 上次完成的命令（完成 3 條指令）：
#    squash 14d7d2b 1ddd
#    squash 3aeab2b asd
# 未剩下任何指令。
# 您在執行將分支 'main' 重定基底到 'aa06fb4' 的動作。
## 這是整合 3 個提交的集合提交。
# 這是第一個提交說明：

[feat]: edit table

# 這是提交說明 #2：

1ddd

# 這是提交說明 #3：

asd

# 請輸入描述您變更的提交訊息。開頭是「#」
# 的行皆會忽略。提交訊息空白則取消本次提交作業。
#
# 日期：  Sun Nov 5 22:19:21 2023 +0530
#
# 互動式重定基底動作正在進行中；至 aa06fb4
# 上次完成的命令（完成 3 條指令）：
#    squash 14d7d2b 1ddd
#    squash 3aeab2b asd
# 未剩下任何指令。
# 您在執行將分支 'main' 重定基底到 'aa06fb4' 的動作。
#
```

#### 調整訊息

```
這是 commit 的名稱

這是子標題1
這是子標題2
```

#### 大功告成～完成合併 commit 的任務～

#### 參考資料

[送 PR 前，使用 Git rebase 來整理你的 commit 吧！](https://medium.com/starbugs/use-git-interactive-rebase-to-organize-commits-85e692b46dd)

[Git | 我以為的 Git Rebase 與和 Git Merge 做合併分支的差異](https://medium.com/starbugs/git-%E6%88%91%E4%BB%A5%E7%82%BA%E7%9A%84-git-rebase-%E8%88%87%E5%92%8C-git-merge-%E5%81%9A%E5%90%88%E4%BD%B5%E5%88%86%E6%94%AF%E7%9A%84%E5%B7%AE%E7%95%B0-cacd3f45294d)
