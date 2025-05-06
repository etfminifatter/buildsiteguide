以下是近期讨论的 **Git 操作命令汇总** 和 **常用 Git 命令清单**，方便你快速查阅和使用：

---

### **近期讨论的 Git 操作命令汇总**

#### **1. 强制覆盖远端分支**
```bash
# 将本地分支强制推送到远端（覆盖远端历史）
git push origin <本地分支名>:<远端分支名> --force
# 示例：用本地 master 覆盖远端 main
git push origin master:main --force
```

#### **2. 合并无关历史的分支**
```bash
# 允许合并无共同历史的分支
git merge <分支名> --allow-unrelated-histories
# 示例：将 master 合并到 main
git merge master --allow-unrelated-histories
```

#### **3. 分支重命名与同步**
```bash
# 重命名本地分支
git branch -m <旧分支名> <新分支名>
# 示例：将 master 重命名为 main
git branch -m master main

# 推送新分支并关联远端
git push -u origin <新分支名>
```

#### **4. 删除远端分支**
```bash
# 删除远端分支
git push origin --delete <分支名>
# 示例：删除远端 dev 分支
git push origin --delete dev
```

#### **5. 解决冲突后继续合并**
```bash
# 解决冲突后标记为已解决
git add .
git commit -m "解决冲突"
```

---

### **常用 Git 命令大全**

#### **基础操作**
| 命令 | 说明 |
|------|------|
| `git init` | 初始化本地仓库 |
| `git clone <仓库URL>` | 克隆远程仓库 |
| `git status` | 查看当前仓库状态 |

#### **分支管理**
| 命令 | 说明 |
|------|------|
| `git branch` | 查看本地分支 |
| `git branch -a` | 查看所有分支（本地+远程） |
| `git checkout <分支名>` | 切换分支 |
| `git checkout -b <新分支名>` | 创建并切换分支 |
| `git merge <分支名>` | 合并分支 |
| `git branch -d <分支名>` | 删除本地分支 |

#### **提交与撤销**
| 命令 | 说明 |
|------|------|
| `git add <文件名>` | 添加文件到暂存区 |
| `git add .` | 添加所有修改到暂存区 |
| `git commit -m "提交信息"` | 提交到本地仓库 |
| `git reset --hard HEAD^` | 撤销最后一次提交（危险！） |

#### **远程仓库操作**
| 命令 | 说明 |
|------|------|
| `git remote -v` | 查看远程仓库地址 |
| `git pull origin <分支名>` | 拉取远程分支更新 |
| `git push origin <分支名>` | 推送本地分支到远程 |
| `git fetch --prune` | 同步远程已删除的分支 |

#### **高级操作**
| 命令 | 说明 |
|------|------|
| `git log --oneline` | 查看简洁版提交历史 |
| `git stash` | 临时保存未提交的修改 |
| `git rebase <分支名>` | 变基操作（谨慎使用） |
| `git tag <标签名>` | 打标签 |

---

### **常用场景速查**
1. **首次推送本地仓库到远程**  
   ```bash
   git remote add origin <仓库URL>
   git push -u origin main
   ```

2. **丢弃本地所有未提交修改**  
   ```bash
   git reset --hard
   git clean -fd
   ```

3. **查看文件修改差异**  
   ```bash
   git diff <文件名>
   ```

4. **回退到指定提交版本**  
   ```bash
   git reset --hard <commit-hash>
   ```

---

### **注意事项**
- **强制推送（`--force`）**：会覆盖远程历史，确保你知道后果！
- **合并冲突**：手动解决后务必 `git add` 和 `git commit`。
- **分支命名**：现代项目推荐用 `main` 替代 `master`。

保存这份清单，遇到问题时随时查阅！ 😊