### 使用vscode完成github仓库拉取与代码提交

1. 从github仓库中拉取代码操作：
    - 点击Code，复制https中的链接
    - 在vscode中 ，使用指令CTRL + SHIFT + P，输入要clone的地址，然后为该项目找一个工作区域，将其pull下来即可
2. 从vscode中提交代码：
    - 使用快捷方式：点击vscode中左侧的源代码管理，点击推送，可直接将代码文件上传到main中
    - 使用指令：CTRL + SHIFT + P，输入git add .，将所有文件添加到暂存区；输入git commit -m "提交说明"，将代码提交到本地仓库；输入git push origin main，将代码推送到远程仓库