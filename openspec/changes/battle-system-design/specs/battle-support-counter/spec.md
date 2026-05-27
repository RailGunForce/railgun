## ADDED Requirements

### Requirement: 清除我方 Debuff
系统 SHALL 允许辅助角色释放技能清除我方角色身上的 Debuff。

#### Scenario: 辅助大招清除 Debuff
- **WHEN** 玩家释放辅助角色大招，目标为我方角色
- **THEN** 我方目标身上所有 Debuff 被清除

#### Scenario: 辅助自动技能清除 Debuff
- **WHEN** 我方角色身上 Debuff 层数达到阈值
- **THEN** 辅助角色自动释放清除技能，移除部分或全部 Debuff

### Requirement: 控制敌人打断连招
系统 SHALL 允许辅助角色通过控制技能打断敌方连招链。

#### Scenario: 控制敌方关键单位
- **WHEN** 辅助角色释放控制技能（眩晕、压制、混乱）命中敌方
- **THEN** 被控制的敌方单位跳过行动，敌方连招链被打断

#### Scenario: 混乱状态攻击友方
- **WHEN** 敌方单位处于混乱状态
- **THEN** 该敌方单位攻击时随机选择敌方（自己人）作为目标

### Requirement: 护盾抵挡伤害
系统 SHALL 允许辅助角色为我方提供护盾，抵挡伤害或免疫控制。

#### Scenario: 护盾抵挡伤害
- **WHEN** 我方角色身上有护盾，受到敌方攻击
- **THEN** 护盾先抵扣伤害，护盾耗尽后才扣血

#### Scenario: 护盾免疫控制
- **WHEN** 我方角色身上有护盾，受到敌方控制技能
- **THEN** 护盾抵消控制效果，角色不进入控制状态

### Requirement: 辅助大招插队
系统 SHALL 允许辅助大招在敌方连招链进行中插队释放。

#### Scenario: 敌方连招中插入辅助大招
- **WHEN** 敌方正在执行连招链，玩家点击辅助大招
- **THEN** 敌方连招暂停，辅助大招立即执行（清除我方 Debuff 或控制敌人）
