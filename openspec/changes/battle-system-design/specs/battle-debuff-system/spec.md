## ADDED Requirements

### Requirement: Debuff 叠层
系统 SHALL 允许相同类型的 Debuff 在目标身上叠加多层。

#### Scenario: 攻击叠加 Debuff
- **WHEN** 角色使用带 Debuff 效果的技能命中敌人
- **THEN** 敌人身上对应 Debuff 层数 +1，显示当前层数

#### Scenario: Debuff 层数显示
- **WHEN** 敌人身上存在 Debuff
- **THEN** 在敌人头顶显示 Debuff 图标和当前层数（如 ⚡x3）

### Requirement: Debuff 阈值触发
系统 SHALL 在 Debuff 层数达到阈值时触发额外效果。

#### Scenario: 带电触发眩晕
- **WHEN** 敌人身上带电层数达到 4 层
- **THEN** 敌人立即进入眩晕状态，持续 1.5 秒

#### Scenario: 潮湿触发减速
- **WHEN** 敌人身上潮湿层数达到 3 层
- **THEN** 敌人立即进入减速状态，移动和攻击速度降低 30%

#### Scenario: 干扰触发攻击削弱
- **WHEN** 敌人身上干扰层数达到 2 层
- **THEN** 敌人攻击力降低 20%

### Requirement: Debuff 反应
系统 SHALL 在不同能力系的 Debuff 组合时触发反应效果。

#### Scenario: 带电遇潮湿触感电扩散
- **WHEN** 带有带电 Debuff 的敌人被流体系技能命中
- **THEN** 触发感电效果，3x3 范围内所有敌人各叠加 1 层带电

#### Scenario: 潮湿遇灼烧触发蒸发
- **WHEN** 带有潮湿 Debuff 的敌人被热能系技能命中
- **THEN** 清除潮湿 Debuff，造成一次额外伤害

#### Scenario: 带电遇干扰触发混乱
- **WHEN** 带有带电 Debuff 的敌人被心理系技能命中
- **THEN** 敌人进入混乱状态，短暂攻击友方

### Requirement: Debuff 持续时间
系统 SHALL 为 Debuff 设置持续时间，超时自动清除。

#### Scenario: Debuff 超时清除
- **WHEN** Debuff 持续时间结束
- **THEN** 该 Debuff 从目标身上移除，层数清零

#### Scenario: 灼烧持续伤害
- **WHEN** 敌人身上有灼烧 Debuff
- **THEN** 每秒造成一次持续伤害，直到 Debuff 消失

### Requirement: 辅助清除 Debuff
系统 SHALL 允许辅助角色清除我方身上的 Debuff。

#### Scenario: 辅助技能清除 Debuff
- **WHEN** 辅助角色释放清除类技能
- **THEN** 我方目标身上所有 Debuff 被清除
