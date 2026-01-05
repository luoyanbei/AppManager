# AppManager

flowchart TD
    A[① 检查环境<br/>WDA 是否可用<br/>大模型是否可用]
    
    A --> B[② 感知输入<br/>截图 + 提示词]
    
    B --> C[③ Planner（大模型）<br/>分析当前界面<br/>生成操作步骤]
    
    C --> D[④ Executor<br/>调用 WDA 操作手机]
    
    D --> E[获取新状态<br/>新的截图 / 页面变化]
    
    E --> F{⑤ 是否完成目标？}
    
    F -- 否 --> B
    F -- 是 --> G[⑥ 结束]
