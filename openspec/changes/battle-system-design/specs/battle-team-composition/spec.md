## ADDED Requirements

### Requirement: 4 人队伍
系统 SHALL 允许玩家组建最多 4 个角色的战斗队伍。

#### Scenario: 队伍编组
- **WHEN** 玩家进入关卡前的编队界面
- **THEN** 可以选择最多 4 个角色加入队伍

#### Scenario: 队伍不足 4 人
- **WHEN** 玩家选择少于 4 个角色进入战斗
- **THEN** 战斗正常进行，只有已选择的角色参战

### Requirement: 角色定位
系统 SHALL 为角色定义不同定位（输出、控制、辅助、坦克），影响连招链设计。

#### Scenario: 输出型角色
- **WHEN** 输出型角色在队伍中
- **THEN** 该角色技能以伤害和 Debuff 叠层为主

#### Scenario: 控制型角色
- **WHEN** 控制型角色在队伍中
- **THEN** 该角色技能以控制效果（眩晕、压制）为主

#### Scenario: 辅助型角色
- **WHEN** 辅助型角色在队伍中
- **THEN** 该角色技能以清除 Debuff、提供护盾、治疗为主

### Requirement: 连招链搭配
系统 SHALL 鼓励玩家根据角色间的连招链关系组建队伍。

#### Scenario: 连招链协同
- **WHEN** 队伍中多个角色的技能可以形成连招链
- **THEN** 战斗中可以触发自动连招，造成更高伤害或控制效果

#### Scenario: 反制搭配
- **WHEN** 队伍中包含辅助角色
- **THEN** 可以通过清除 Debuff 或控制敌人打断敌方连招

### Requirement: 敌方配队决定难度
系统 SHALL 根据敌方配队设计关卡难度。

#### Scenario: 简单难度
- **WHEN** 敌方配队为纯输出，无配合
- **THEN** 玩家可硬扛输出，不需要特殊策略

#### Scenario: 中等难度
- **WHEN** 敌方配队包含 1 个控制型敌人
- **THEN** 玩家需要带辅助角色清除 Debuff

#### Scenario: 困难难度
- **WHEN** 敌方配队有完整连招链
- **THEN** 玩家必须用控制技能打断敌方连招

#### Scenario: Boss 难度
- **WHEN** 敌方配队有连招链 + 辅助反制
- **THEN** 玩家需要预判敌方行动，选择最佳时机放大招
