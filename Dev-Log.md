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

### 日志 #2: 本地运行CS336讲座的标准操作流程 (SOP)

**日期:** 2025-07-02

**目标:** 固化一套完整的标准操作流程，用于将官方 `lectures` 仓库克隆到本地，并成功运行任意一节课的交互式界面。

---

**标准操作流程 (Standard Operating Procedure):**

1.  **克隆并进入仓库 (Clone and Enter Repository)**
    * 使用SSH协议克隆官方课程仓库。
    ```bash
    git clone git@github.com:stanford-cs336/spring2025-lectures.git
    cd spring2025-lectures/
    ```

2.  **创建并激活Python虚拟环境 (Setup Python venv)**
    * 为项目创建一个隔离的Python环境。
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```
    * *成功后，命令行提示符前会出现`(venv)`标识。*

3.  **安装Python依赖 (Install Python Dependencies)**
    * 首次安装时因网络问题连接 `pypi.org` 超时，通过 `-i` 参数临时指定清华大学TUNA镜像源成功解决。
    ```bash
    pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
    ```
    * **[未来优化]**: 可通过修改 `~/.pip/pip.conf` 文件来永久配置镜像源，避免每次手动指定。

4.  **安装前端依赖 (Install Frontend Dependencies)**
    * 此步骤为前端播放器安装所需库，仅需在项目初次设置时执行一次。
    ```bash
    cd trace-viewer/
    npm install
    cd .. 
    ```

5.  **启动服务并查看讲座 (Run Servers & View Lecture)**
    * 此流程需要**两个并行运行的终端窗口**。

    * **终端 1 (用于生成讲座数据):**
        * 路径：`~/spring2025-lectures/`
        * 确保激活虚拟环境：`source venv/bin/activate`
        * 执行编译脚本 (以Lec 01为例):
        ```bash
        python3 execute.py --path lecture_01.py
        ```

    * **终端 2 (用于启动前端播放器):**
        * 路径：`~/spring2025-lectures/trace-viewer/`
        * 执行启动命令:
        ```bash
        npm run dev
        ```

    * **浏览器 (Browser):**
        * 打开浏览器并访问以下地址，即可查看对应的交互式讲座。
        ```
        http://localhost:5173/?trace=../var/traces/lecture_01.json
        ```
        * *提示：学习后续课程时，只需将两个终端命令和URL中的 `lecture_01` 替换为相应的课程编号即可。*