# Learning Skill

用于一个 Lecture（一周课程内容）的 AI 辅助学习。默认中文讲解，沿用课程术语与符号。

## Skill 文件

入口：[SKILL.md](.agents/skills/learning-skill/SKILL.md)。完整目录位于 `.agents/skills/learning-skill/`，包含教学和记录细则以及两份空白模板。

下载完整文件包：[learning-skill.zip](dist/learning-skill.zip)。压缩包包含主文件、配套规则和记录模板。

```text
.agents/skills/learning-skill/
├── SKILL.md
├── references/
│   ├── teaching-and-assessment.md
│   └── state-and-review.md
└── assets/templates/
    ├── progress.md
    └── learning-gaps.md
```

在支持项目级 `.agents/skills` 的宿主中，可以从本项目使用；其他支持 Agent Skills 的宿主可将整个 `learning-skill` 目录放入其 Skill 目录。配套文件需要一起保留。这里提供的是文件包，是否被当前宿主自动发现取决于其加载机制。

## 使用示例

- “使用 learning-skill 带我学习 Lecture 3，PPT 和补充讲义在这个目录。”
- “继续上次没有学完的 Lecture。”
- “按 Lecture 复习上一讲，再开始新课。”
- “把整体规划中的这个知识点改为核心内容，然后按规划开始。”

提供本讲的 PPT 和对应补充材料；有 midterm、final 或评分标准时一并提供，供 AI 校准出题方式。没有考试材料也能学习，但不能声称已经匹配教授的考试风格。

## 已确认的行为

1. 完整阅读本讲材料后，先展示可修改的章节规划、核心／补充／待确认分类及依据。
2. 所有内容完整教学、同等深度、逐项检测；分类不影响覆盖或通过标准。
3. 每个小章节结束立即检测，所有要求掌握的能力独立通过后推进；主动跳过保留未掌握记录。
4. 整个 Lecture 学完后先独立完成整套检测，再统一反馈和补教复测。
5. 出题参考课程及考试的考查方式，按需搜索网络，核验题目和答案；不能仅换数字或措辞。
6. 主动保存最小进度和有证据的不足；反复询问先验证，不直接判为理解不足。
7. 下次学习可选择复习上一 Lecture，先检查回忆与应用，再补讲。

教学互动提出任务后等待学生真实作答。暂停会话保留 Lecture 原学习阶段；进行中的检测保存固定试卷、评分依据和已有答案，跨会话按原版本继续。

实际学生记录在课程工作目录的 `.learning/<course-id>/` 中初始化，包含 `progress.md` 和 `learning-gaps.md`。本项目目前只提供空白模板，没有学生学习记录。

当前范围为 Lecture 学习与复习，作业辅导另设 Skill；不包含 flashcard 或独立 paper-reader 模块。

## 设计参考

规则根据本次讨论独立编写，参考了 [Jacquard Labs Study Skills](https://github.com/jacquardlabs/study-skills) 的模块组织，以及 [Ericsson 与 Harwell 对刻意练习的说明](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2019.02396/full)。这些项目或文章不是执行依赖。
