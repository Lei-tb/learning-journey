2026/4/18

---

1.新建工程

![1776509007547](git.assets/1776509007547.png)

<img src="git.assets/1776509502684.png" alt="1776509502684" style="zoom: 50%;" />

2.拉取

![1776509743733](git.assets/1776509743733.png)

3.提交

(1)

**git status 是来确定在哪个分支的，同时给出三种情况：**

1. **改变还没准备提交 → 可以 add 或 restore**
2. **未被追踪的新文件 → 可以 add 追加**
3. **没有标记 → 提示你要 add**

<img src="git.assets/1776511306301.png" alt="1776511306301" style="zoom: 67%;" />

(2) 创建新分支和切换分支，每个分支是独立的

![1776516227160](git.assets/1776516227160.png)

![1776516311164](git.assets/1776516311164.png)



合并

 Git 只合并 ** 已经提交（commit）** 的版本，暂存区的内容是不能合并的。 

 如果你想在 GitHub 上备份你的 `base` 分支、或者让别人也能看到你的工作，就执行  git push origin base 

## 把 base 分支 → 合并到 main 分支

## 1. 先切换到【你要合并进去的目标分支】

```
git checkout main
```

## 2. 执行合并命令（把 base 合进来）

```
git merge base
```

## 3. 推送到 GitHub（让云端也更新）

```
git push origin main
```

commit必须由-m否则不让提交

push上传

时间轴

不小心将重要文件删除了 eg:readme.md被删了

![1776514216392](git.assets/1776514216392.png)



### 1. 改了文件

**状态：红色，未暂存**

→ 想撤销：

bash



运行









```
git restore 文件名
```

### 2. 执行了 git add

**状态：绿色，已暂存**

→ 想撤销 add（回到修改后的状态，不丢代码）：

bash



运行









```
git restore --staged 文件名
```

### 3. 执行了 commit

→ 想撤销版本：

bash



运行









```
git reset
```

 git revert -m 1 HEAD 









> 如果我已经提交到 base 里面并且已经和 main 合并，发现合并的代码有问题，我可以直接 reset main 分支回到上一次提交的时候。然后再进行修改 base 分支是吧

### 最终标准答案：

**对！就是这样！**

流程正确到不能再正确：

1. 合并 `base → main` 后发现错了 ❌

2. 立刻切换到 main

   bash

   

   运行

   

   

   

   

   ```
   git checkout main
   ```

   

3. 让 main 

   回滚到合并之前

   bash

   

   运行

   

   

   

   

   ```
   git reset --hard HEAD^
   ```

   

4. 回到 

   ```
   base
   ```

    去修改、修复

   bash

   

   运行

   

   

   

   

   ```
   git checkout base
   ```

   

5. 改好后，重新合并到 main 

 reset 只会动你当前所在的分支！不会影响其他分支！ 



 你修改代码时，必须确认当前在哪个分支！ 



## 你在哪个分支上执行 git add /commit

## 这些修改就归哪个分支！**





**项目本身是一个整体**

**内容被拆成好几条平行的线来维护**

main是正式版

 main分支里面是整合的完整代码，这样的话，便于每个人负责一块，有问题，main函数扯一下，相应的人直接改 

 分支分工 → 单独开发 → 合并整合 → 出错回滚 



 我add之后又修改了内容

![1776517981902](git.assets/1776517981902.png)



你上一次已经 `commit`

但你**又改了一点代码****新的提交**只想

→ 这就是 `--amend`































































