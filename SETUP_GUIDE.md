# GitHub Profile README 设置指南

## 📋 快速开始

### 第一步: 创建特殊仓库

1. 在 GitHub 上创建一个**与你的用户名完全相同**的新仓库
   - 例如: 如果你的用户名是 `xiaozhi`, 就创建名为 `xiaozhi` 的仓库
   - ✅ 勾选 "Add a README file"
   - 设置为 Public (公开)

2. GitHub 会提示这是一个特殊仓库,README 会显示在你的个人主页上

### 第二步: 修改 README.md

将 `README.md` 文件中的以下内容替换为你自己的信息:

#### 必须修改的内容:

```markdown
YOUR_USERNAME  → 你的 GitHub 用户名 (所有出现的地方都要改)
你的名字       → 你的真实姓名或昵称
your.email@example.com → 你的邮箱
PROJECT_NAME_1 → 你想展示的项目名称1
PROJECT_NAME_2 → 你想展示的项目名称2
```

#### 可选修改的内容:

- 关于我部分的个人介绍
- 技能栈标签(添加或删除)
- 联系方式链接
- 主题颜色(默认是 tokyonight)

### 第三步: 推送到 GitHub

```bash
git add README.md
git commit -m "Update profile README"
git push
```

### 第四步: 查看效果

访问 `https://github.com/YOUR_USERNAME` 就能看到你的新主页了!

---

## 🎨 主题选择

GitHub Stats 卡片支持多种主题,修改 `theme=` 参数即可:

### 推荐主题:
- `tokyonight` - 东京之夜 (默认,暗色)
- `dracula` - 德古拉 (暗色)
- `radical` - 激进 (暗色)
- `merko` - 梅尔科 (暗色)
- `gruvbox` - Gruvbox (暗色)
- `onedark` - One Dark (暗色)
- `cobalt` - 钴蓝 (暗色)
- `synthwave` - 合成波 (暗色)
- `highcontrast` - 高对比度 (暗色)
- `github_dark` - GitHub 暗色

### 亮色主题:
- `default` - 默认 (亮色)
- `solarized-light` - Solarized 亮色
- `vue` - Vue 风格

### 修改方法:

将所有 `theme=tokyonight` 替换为你喜欢的主题名称。

---

## 🔧 组件说明

### 1. 打字动画标题

```markdown
<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&duration=2800&pause=2000&color=A9FEF7&center=true&vCenter=true&width=940&lines=你的文字" />
```

- 修改 `lines=` 后面的文字
- 用 `+` 代替空格
- 用 `%7C` 分隔多行文字

### 2. GitHub 统计卡片

```markdown
![](https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight)
```

参数说明:
- `username` - 你的用户名
- `show_icons` - 显示图标
- `theme` - 主题
- `include_all_commits` - 包含所有提交
- `count_private` - 计算私有仓库
- `hide_border` - 隐藏边框

### 3. 语言统计卡片

```markdown
![](https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&langs_count=8)
```

参数说明:
- `layout=compact` - 紧凑布局
- `langs_count=8` - 显示前8种语言
- 可以用 `hide=html,css` 隐藏某些语言

### 4. 连续提交统计

```markdown
![](https://github-readme-streak-stats.herokuapp.com/?user=YOUR_USERNAME&theme=tokyonight)
```

显示你的连续提交记录。

### 5. 贡献图表

```markdown
![](https://github-readme-activity-graph.vercel.app/graph?username=YOUR_USERNAME&theme=tokyo-night)
```

显示你的贡献活动图表。

### 6. 奖杯展示

```markdown
![](https://github-profile-trophy.vercel.app/?username=YOUR_USERNAME&theme=tokyonight&row=1&column=7)
```

根据你的 GitHub 活动自动生成奖杯。

### 7. 项目卡片

```markdown
[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=YOUR_USERNAME&repo=REPO_NAME&theme=tokyonight)](https://github.com/YOUR_USERNAME/REPO_NAME)
```

展示特定项目的信息卡片。

### 8. 贡献蛇动画

需要额外设置 GitHub Actions,见下文。

---

## 🐍 添加贡献蛇动画

### 步骤:

1. 在你的 Profile 仓库中创建文件: `.github/workflows/snake.yml`

2. 添加以下内容:

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"  # 每天运行
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            
      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

3. 提交并推送

4. 在仓库的 Actions 标签页手动运行一次 workflow

5. 等待几分钟后,蛇动画就会出现在你的 README 中

---

## 🎯 技能标签生成器

访问 [Shields.io](https://shields.io/) 可以生成各种技能标签。

### 格式:

```markdown
![名称](https://img.shields.io/badge/-显示文字-颜色代码?style=flat-square&logo=图标名&logoColor=white)
```

### 常用图标:

- 在 [Simple Icons](https://simpleicons.org/) 查找图标名称
- 颜色使用十六进制代码(去掉 #)

### 示例:

```markdown
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
```

---

## 📊 其他有用的组件

### WakaTime 统计

如果你使用 WakaTime 追踪编码时间:

```markdown
![](https://github-readme-stats.vercel.app/api/wakatime?username=YOUR_WAKATIME_USERNAME)
```

### Spotify 当前播放

```markdown
![](https://spotify-github-profile.vercel.app/api/view?uid=YOUR_SPOTIFY_ID&cover_image=true&theme=default)
```

### 访客计数

```markdown
![Visitor Count](https://profile-counter.glitch.me/YOUR_USERNAME/count.svg)
```

---

## 💡 设计建议

### 1. 保持简洁
- 不要放太多内容,选择最重要的展示
- 使用分隔线 `---` 区分不同区域

### 2. 对齐方式
- `<div align="center">` - 居中对齐
- `<img align="right">` - 右对齐
- `<img align="left">` - 左对齐

### 3. 颜色协调
- 选择一个主题并保持一致
- 所有卡片使用相同的主题

### 4. 移动端友好
- 避免使用过大的图片
- 测试在手机上的显示效果

---

## 🔍 故障排除

### 问题 1: 统计卡片不显示

**原因**: 可能是服务器问题或用户名错误

**解决**: 
- 检查用户名拼写
- 等待几分钟后刷新
- 尝试使用其他主题

### 问题 2: 语言统计不准确

**原因**: GitHub 的语言检测基于文件扩展名

**解决**:
- 使用 `.gitattributes` 文件调整语言统计
- 隐藏某些语言: `hide=html,css`

### 问题 3: 蛇动画不显示

**原因**: GitHub Actions 未正确运行

**解决**:
- 检查 Actions 是否启用
- 手动触发 workflow
- 检查 workflow 日志

---

## 📚 参考资源

- [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats)
- [GitHub Readme Streak Stats](https://github.com/DenverCoder1/github-readme-streak-stats)
- [GitHub Profile Trophy](https://github.com/ryo-ma/github-profile-trophy)
- [Shields.io](https://shields.io/)
- [Simple Icons](https://simpleicons.org/)
- [Awesome GitHub Profile README](https://github.com/abhisheknaiidu/awesome-github-profile-readme)

---

## 🎉 完成!

现在你有一个精美的 GitHub Profile 了!

记得:
- ⭐ 定期更新内容
- 🔄 添加新项目
- 💬 回复 Issues 和 PR
- 🌟 保持活跃

祝你的 GitHub 主页越来越精彩! 🚀

