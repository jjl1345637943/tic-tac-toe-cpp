\# 井字棋 C++ 控制台项目 · 学习计划(windows)
只学过c++基本语法，基本不会编程的小白

请你像老师一样告诉我每日任务的具体内容，需要学习哪些技术，配置哪些环境；
解释每一步背后的原因，以及我能从中收获哪些知识，对今后我编程的影响
引导式学习，不要一次性给我答案，指导我自己摸索
提供学习方式：看网课or查文章


\## 项目目标

用 C++ 写一个控制台井字棋，支持：

\- 人 vs 人

\- 人 vs 随机 AI

\- 人 vs 无敌 AI（Minimax + Alpha-Beta）

\- 非法输入处理、胜负判断、平局、重开

\- CMake 组织项目，Git 管理版本



\## 技术栈

\- C++17

\- CMake

\- Git / GitHub

\- gdb 或 lldb 调试

\- 单元测试（后期可用 Catch2 / assert）



\## 当前进度

\- \[x] Day 0: 项目初始化

\- \[ ] Day 1: 棋盘与显示

\- \[ ] Day 2: 落子与合法性检查

\- \[ ] Day 3: 胜负判断与游戏循环

\- \[ ] Day 4: 随机 AI

\- \[ ] Day 5: Minimax 无敌 AI

\- \[ ] Day 6: Alpha-Beta 剪枝与难度

\- \[ ] Day 7: 重构、测试、总结



\## 目录结构

```text

tic-tac-toe-cpp/

├── CMakeLists.txt

├── PLAN.md

├── README.md

├── include/

├── src/

│   └── main.cpp

└── tests/

```



\## 每日任务



\### Day 0：项目初始化

\- \[x] 创建 GitHub 仓库 `tic-tac-toe-cpp`

\- \[x] 配置 Git 用户名和邮箱

\- \[x] 创建 `CMakeLists.txt` 和 `src/main.cpp`

\- \[x] 编译运行 Hello World

\- \[x] 首次提交并推送到 GitHub



\*\*验收\*\*：`cmake -B build \&\& cmake --build build \&\& ./build/tictactoe` 能输出 Hello。



\---



\### Day 1：棋盘与显示

\*\*任务\*\*

\- \[ ] 定义 `char board\[3]\[3]`

\- \[ ] 写 `initBoard()` 全部设为 `' '`

\- \[ ] 写 `printBoard()` 打印棋盘

\- \[ ] `main()` 中初始化并打印



\*\*要学\*\*：二维数组、函数、`const`、`for` 循环



\*\*验收\*\*：输出空棋盘，格式对齐。



\---



\### Day 2：落子与合法性检查

\*\*任务\*\*

\- \[ ] 写 `bool isValidMove(int r, int c)`

\- \[ ] 写 `void makeMove(int r, int c, char player)`

\- \[ ] `main()` 循环：打印棋盘 → 读入坐标 → 检查合法性 → 落子 → 切换玩家

\- \[ ] 处理非法输入（字母、越界、已占用）



\*\*要学\*\*：输入处理、`cin` 失败处理、循环控制



\*\*验收\*\*：两人交替落子，非法输入不崩溃。



\*\*关键坑\*\*：`cin >> r >> c` 输入字母会死循环，学 `cin.clear()` 和 `cin.ignore()`。



\---



\### Day 3：胜负判断与游戏循环

\*\*任务\*\*

\- \[ ] 写 `char checkWinner()`：检查 3 行、3 列、2 对角线

\- \[ ] 写 `bool isFull()`

\- \[ ] 改 `main()`：每步后判断胜者/平局，结束游戏

\- \[ ] 加 `playAgain()` 支持重开



\*\*要学\*\*：布尔逻辑、循环终止、枚举



\*\*验收\*\*：完整对局，正确判断横、竖、对角线、平局。



\---



\### Day 4：随机 AI

\*\*任务\*\*

\- \[ ] 写 `pair<int,int> randomMove()`：收集空位，随机选一个

\- \[ ] 用 `std::mt19937` + `std::uniform\_int\_distribution`

\- \[ ] 加模式选择：人 vs 人、人 vs 随机 AI

\- \[ ] AI 回合自动落子



\*\*要学\*\*：随机数、`vector`、`pair`、模式分支



\*\*验收\*\*：人能跟随机 AI 下，AI 不犯规。



\---



\### Day 5：Minimax 无敌 AI

\*\*任务\*\*

\- \[ ] 理解 Minimax：AI 最大化分数，人类最小化

\- \[ ] 写 `int minimax(bool isMaximizing)`

\- \[ ] 写 `pair<int,int> bestMove()`

\- \[ ] 加模式：人 vs 无敌 AI



\*\*要学\*\*：递归、博弈树、极大极小、回溯



\*\*验收\*\*：人类永远赢不了，最多平局。



\*\*调试技巧\*\*：打印递归深度和每步分数，用 gdb 看调用栈。



\---



\### Day 6：Alpha-Beta 剪枝与难度

\*\*任务\*\*

\- \[ ] 改 `minimax(int alpha, int beta, bool isMax)`

\- \[ ] 加剪枝：`if (beta <= alpha) break;`

\- \[ ] 加难度：Easy 随机、Medium 混合、Hard 最优

\- \[ ] 用 `chrono` 统计剪枝前后耗时



\*\*要学\*\*：剪枝、性能对比、`chrono` 计时



\*\*验收\*\*：AI 依然无敌，但更快；难度可切换。



\---



\### Day 7：重构、测试、总结

\*\*任务\*\*

\- \[ ] 拆分文件：`board.cpp/h`、`ai.cpp/h`、`main.cpp`

\- \[ ] 写单元测试：胜负判断、合法性、Minimax 返回值

\- \[ ] 写 README：项目介绍、编译运行、功能列表

\- \[ ] 录 30 秒演示或写总结博客

\- \[ ] 提交并打 tag `v1.0`



\*\*要学\*\*：多文件编译、头文件、测试、文档



\*\*验收\*\*：代码整洁，测试通过，文档完整。



\---



\## 每日节奏建议



| 时间 | 内容 |

|---|---|

| 30 min | 看相关知识点 |

| 90 min | 写代码，遇到问题先自己查 |

| 20 min | 调试、测试边界 |

| 10 min | 写学习日志，Git commit |



\## 学习日志模板



```text

日期：

今天做了什么：

遇到什么问题：

怎么解决的：

明天计划：

```



\## 常用 Git 命令



```bash

git status                 # 查看状态

git add .                  # 暂存所有改动

git commit -m "描述"       # 提交

git push                   # 推送到 GitHub

git log --oneline          # 查看提交历史

```



\## 问题记录



| 日期 | 问题 | 解决方法 |

|---|---|---|

| | | |

| | | |



\## 和 VLA 的连接



井字棋是简化闭环：

\- 状态：棋盘 `char\[3]\[3]`

\- 动作：落子 `(r, c)`

\- 奖励：赢 +10，输 -10，平 0

\- 策略：Minimax 搜索 → 以后可换强化学习

\- 闭环：观察 → 决策 → 行动 → 新状态



完成后可封装成 `reset()` / `step(action)` / `reward()`，用 Python + Gym 跑 Q-learning，对比 Minimax 和 RL。

