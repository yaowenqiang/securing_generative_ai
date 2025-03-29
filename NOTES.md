# Securing Generative AI

SLM(Small Language Model)

## Three ways of using AI

+ Train a model from scratch
+ Fine Tune a model
  + Llama
  + Mistral
  + Phi
  + Phi2
+ RAG

## OWASP Top 10 for LLM Applications

### ​**2025年OWASP LLM应用十大安全风险对比表**  
（基于2023年与2025年版本核心变化）

| 2025版风险项               | 2023版对应项/变化               | 关键更新与新增场景                                                                 |
|------------------------------|----------------------------------|----------------------------------------------------------------------------------|
| ​**LLM01: 提示注入**          | LLM01: 提示词注入               | 扩展至多模态提示注入、RAG文档篡改注入、对抗性后缀攻击及多语言混淆攻击[1,3,6](@ref)         |
| ​**LLM02: 敏感信息披露**      | LLM06: 敏感信息披露             | 优先级跃升至第二位，新增专有算法暴露风险，强化差分隐私、联合学习等防御措施[1,3,6](@ref)       |
| ​**LLM03: 供应链漏洞**        | LLM05: 供应链漏洞               | 新增Lora适配器投毒、设备端风险及协作开发流程漏洞，聚焦开源模型与第三方组件安全性[3,6](@ref)      |
| ​**LLM04: 数据和模型投毒**    | LLM03: 训练数据投毒             | 扩展至模型投毒（后门触发器植入、恶意序列化技术），强调生产环境对抗性输入风险[1,3,6](@ref)    |
| ​**LLM05: 不当输出处理**      | LLM02: 不安全的输出处理         | 优先级下降但范围扩大，涵盖钓鱼攻击、路径遍历漏洞及SQL注入等传统攻击通过LLM输出的新形式[3,6](@ref) |
| ​**LLM07: 系统提示泄露**      | ​**新增**                        | 系统提示中硬编码API密钥、数据库凭证等敏感信息，攻击者通过逆向工程或诱导输出窃取指令[1,3,6](@ref) |
| ​**LLM08: 向量和嵌入弱点**    | ​**新增**                        | RAG技术中向量生成、存储或检索漏洞，导致跨上下文信息泄露（如简历隐藏指令攻击）[1,3,6](@ref)    |
| ​**LLM09: 虚假信息**          | LLM09: 过度依赖                 | 涵盖模型幻觉与训练数据偏差的综合风险，需结合RAG和人工验证降低误导性输出[1,3,6](@ref)        |
| ​**LLM10: 无界消费**          | LLM04: 拒绝服务+LLM10: 模型盗窃 | 整合资源滥用、经济损失、模型盗窃等场景，需限制输入规模并监控异常消耗[1,3,6](@ref)          |

### ​**关键变化说明**  
1. ​**新增风险项**：  
   - ​**系统提示泄露（LLM07）​**：由系统提示中硬编码敏感信息引发，需分离业务规则至外部策略引擎[3,6](@ref)。  
   - ​**向量和嵌入弱点（LLM08）​**：针对RAG技术的攻击（如文档投毒），需实施细粒度访问控制[3,6](@ref)。  

2. ​**优先级调整**：  
   - ​**敏感信息披露（LLM02）​**：因专有算法泄露风险上升，需结合同态加密等技术保护数据[1,6](@ref)。  
   - ​**供应链漏洞（LLM03）​**：开源模型（如DeepSeek）普及后，Lora适配器投毒成为新威胁[3,6](@ref)。  

3. ​**技术融合风险**：  
   - 多模态提示注入需结合代码分析与语义验证防御[1,3](@ref)。  
   - 自主代理系统（Autonomous Agents）的过度代理风险扩展至多代理协作场景[3,6](@ref)。  

> 完整风险详情及防御方案可参考：[OWASP LLM Top10 2025官方文档](参考链接)[1,2,3,6](@ref)


> https://genai.owasp.org/

> https://atlas.mitre.org

> https://attack.mitre.org


## Understanding Prompt Injection & Insecure Output Handling


> https://github.com/prompt-security/ps-fuzz
> https://github.com/controllability/jailbreak-evaluation

### Using ChatML for OpenAI API Calls to indicate to the LLM the Source of Prompt Input


#### System Prompts

> langsmith
> smith.langchain.com

> langchain hub

> Meta Prompt Extraction

> https://www.robustintelligence.com/

> Toxicity(毒性)

#### Enforcing Privilege Control on LLM Access to Backend Systems

+ ABAC
+ RBAC

### Best Practice Around API Security


> ASVS(Application Security Verification Standard)

> https://github.com/OWASP/ASVS

+ ASVS
+ Token rotation
+ Good crypto
+ MOnitoring And Auditting

#### How to secure API Tokens

### Insecure Output Handling Attacks

Use Secure Vaults, Avoid Hardcoding



> ZTA(Zero Trust Archtecture)

## Training Data Poisoning, Model Denial of Service & Supply Chain Vulnerabilities

>https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/

### Inventory

> SPDX
> CycloneDX
> SBDM
> AI BOM



