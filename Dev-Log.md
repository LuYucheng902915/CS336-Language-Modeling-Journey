### 日志 #1: 首次将本地仓库关联到GitHub并解决推送问题

**日期:** 2025-07-02

* **目标:**
    记录将一个已在本地初始化的Git仓库，成功关联到一个全新的GitHub远程仓库，并完成首次推送的完整流程。

* **标准操作流程 (SOP):**

    1.  **本地仓库准备:**
        - 在本地项目文件夹内，通过 `git init` 初始化仓库。
        - 完成项目结构搭建、文件创建，并执行 `git add .` 和 `git commit -m "Initial commit"` 完成首次本地提交。

    2.  **GitHub端操作:**
        - 在GitHub官网创建一个新的、**空的**远程仓库（不勾选任何初始化选项）。
        - 创建成功后，复制仓库的URL。

    3.  **本地与远程关联:**
        - **初始尝试 (使用HTTPS):**
          按照GitHub官方指引，使用HTTPS地址关联远程仓库。
          ```bash
          # 关联远程仓库
          git remote add origin [https://github.com/LuYucheng902915/CS336-Language-Modeling-Journey.git](https://github.com/LuYucheng902915/CS336-Language-Modeling-Journey.git)
          
          # 重命名主分支为main (推荐)
          git branch -M main
          ```

* **遇到的问题与解决方案:**

    * **问题描述:**
      执行首次推送命令 `git push -u origin main` 时，终端长时间卡住，没有任何响应。

    * **解决方案与流程优化:**
      判断问题可能源于WSL网络环境下HTTPS协议传输不稳定。决定切换到更稳定高效的SSH协议作为标准工作流。

      1.  **将远程URL从HTTPS切换为SSH:** (前提是本地SSH密钥已配置到GitHub)
          ```bash
          git remote set-url origin git@github.com:LuYucheng902915/CS336-Language-Modeling-Journey.git
          ```
      2.  **再次推送:**
          ```bash
          git push -u origin main
          ```
      3.  **结果:**
          切换到SSH后，推送瞬间完成，问题解决。

* **经验总结:**
    这是一次非常有价值的实践。它不仅完整梳理了从本地到远程的首次关联流程，更重要的是验证了一个关键经验：**在WSL环境中，当遇到Git网络问题时，应优先使用SSH协议。** 这将成为我未来所有项目的标准操作流程，以确保开发过程的顺畅。