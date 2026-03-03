### 使用github完成团队代码协作

1. 创建一个仓库
2. 进入该仓库，点击setting，点击Collaborators and teams，进入该页面后点击Add people，输入成员的username 和邮箱
3. 选择成员权限级别：
        Read: 只读   Triage: 可管理 issue 和 PR    Write: 可推送代码（推荐）    Maintain: 可管理仓库设置   Admin: 完全控制

4. 团队协作工作流，推荐模式：Forking 工作流 或 分支保护工作流
    ```
    方案 A：分支保护工作流（小团队 2-5 人）
        main 分支（受保护，不能直接推送）
                 ↑
         feature-xxx 分支（个人开发）
    设置分支保护：
        1. 仓库 → Settings → Branches
        2. Branch protection rules → Add rule
        3. 输入  main ，勾选：
        ✅ Require a pull request before merging（需要 PR）
        
        ✅ Require approvals（需要 1 人审核）
        
        ✅ Require status checks to pass（可选，CI 检查）
        成员日常操作：
        bash
        # 1. 克隆仓库（每个成员执行）
        git clone https://github.com/团队账号/TeamProject.git
        cd TeamProject

        # 2. 创建个人开发分支
        git checkout -b feature-login-张三

        # 3. 开发并提交
        git add .
        git commit -m "feat: 添加登录页面"

        # 4. 推送到远程
        git push -u origin feature-login-张三

        # 5. 在 GitHub 发起 Pull Request → 请求合并到 main
        # 6. 其他成员 Code Review → 批准 → 合并
    ```