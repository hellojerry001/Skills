# Professional Prompt Patterns

专业指令类 Prompt 用于给 AI 工具（如 Midjourney、Claude、GPT、设计工具等）下达精确的任务指令。特点是清晰、具体、可执行。

## 核心原则

### 1. 明确任务目标
清楚说明要完成什么任务，避免模糊表达

### 2. 提供关键约束
列出必须遵循的要求、参数、限制

### 3. 结构化组织
将复杂指令拆解为清晰的部分

### 4. 使用专业术语
准确使用领域内的专业词汇

## 模式 1：设计分析型

适用于：UI/UX 设计分析、视觉设计解构、设计系统创建

### 结构模板
```
[动词短语：分析/创建/解构] the [对象] of [输入描述] to [输出目标].

Pay close attention to:
- [关键要素 1]
- [关键要素 2]
- [关键要素 3]
- [关键要素 N]

[可选：额外要求或输出格式说明]
```

### 示例：设计系统分析
```
Deeply analyze the design of the attached screenshot to create a design system layout of every UI component needed in a design system for a SaaS product service.

Pay close attention to:
- spacing
- fonts
- colors
- design style
- design principles
```

### 写作要点
1. **动词要精准**：analyze（分析）、extract（提取）、create（创建）、deconstruct（解构）
2. **要素要完整**：列出所有需要关注的维度
3. **上下文要清晰**：说明分析对象和目标用途

## 模式 2：图像生成型

适用于：Midjourney、DALL-E、Stable Diffusion 等图像生成工具

### 结构模板
```
[主体描述], [风格描述], [技术参数], [质量要求]

或者：

Create [主体] in [风格] style, featuring:
- [特征 1]
- [特征 2]
- [特征 3]

Technical requirements:
- [参数 1]
- [参数 2]
```

### 示例：概念设计
```
A futuristic smart home interface, minimalist sci-fi style, holographic UI elements floating in mid-air, soft blue and white color palette, high detail, 8k resolution, rendered in Octane
```

### 写作要点
1. **主体清晰**：准确描述要生成的核心对象
2. **风格明确**：使用可识别的风格标签（minimalist、photorealistic、art nouveau）
3. **参数具体**：包含分辨率、光照、材质等技术要求

## 模式 3：内容生成型

适用于：文本生成、代码生成、数据分析等任务

### 结构模板
```
[任务动词] [输出类型] that [功能/目的].

Requirements:
- [需求 1]
- [需求 2]
- [需求 3]

Format:
[输出格式说明]

Constraints:
- [约束条件 1]
- [约束条件 2]
```

### 示例：代码生成
```
Generate a React component that displays a responsive pricing table.

Requirements:
- Three pricing tiers (Basic, Pro, Enterprise)
- Toggle between monthly/annual billing
- Highlight the "Pro" tier as recommended
- Mobile-responsive design

Format:
- Use functional components with hooks
- Include TypeScript types
- Add inline comments for key logic

Constraints:
- No external UI libraries
- Maximum 200 lines of code
```

### 写作要点
1. **任务明确**：generate、create、write、build
2. **需求分层**：功能需求、格式要求、约束条件分开列出
3. **可验证性**：每个要求都应该可以验证是否完成

## 模式 4：数据处理型

适用于：数据分析、信息提取、内容转换

### 结构模板
```
[处理动词] the [数据类型] from [来源] and [输出动作].

Focus on:
- [关注点 1]
- [关注点 2]

Output format:
[格式描述]

Additional requirements:
- [额外要求]
```

### 示例：数据提取
```
Extract all product features from the attached product page and organize them into a comparison table.

Focus on:
- Technical specifications
- Pricing information
- Unique selling points

Output format:
- Markdown table
- Features as rows, products as columns
- Include source links

Additional requirements:
- Highlight premium features
- Add brief explanations for technical terms
```

### 写作要点
1. **动词清晰**：extract、transform、analyze、summarize
2. **来源明确**：清楚说明数据来自哪里
3. **格式具体**：详细说明输出的结构和格式

## 通用优化技巧

### 1. 使用分层结构
```
不推荐：
"Create a logo that's modern and clean with blue colors"

推荐：
"Create a modern logo for a tech startup.

Style requirements:
- Minimalist design
- Sans-serif typography
- Geometric shapes

Color palette:
- Primary: Deep blue (#1a73e8)
- Secondary: Light gray (#f1f3f4)

Deliverables:
- SVG format
- Transparent background
- 500x500px"
```

### 2. 提供参考标准
```
不推荐：
"Make it look professional"

推荐：
"Use a visual style similar to modern SaaS products like Notion or Linear"
```

### 3. 明确优先级
```
Must have:
- [核心要求]

Nice to have:
- [可选要求]
```

### 4. 包含负面指令
```
Avoid:
- [不想要的元素]
- [要避免的风格]
```

## 领域专用术语库

### UI/UX 设计
- Layout: grid system, spacing, alignment, hierarchy
- Typography: font family, weight, size, line height, letter spacing
- Colors: palette, contrast ratio, accessibility
- Components: buttons, cards, modals, navigation
- Interaction: hover states, transitions, animations

### 图像生成
- Style: photorealistic, anime, oil painting, watercolor, low poly
- Lighting: soft light, dramatic lighting, golden hour, studio lighting
- Composition: rule of thirds, symmetry, depth of field
- Quality: 4k, 8k, high detail, sharp focus, HDR

### 内容创作
- Tone: professional, casual, friendly, authoritative
- Structure: listicle, tutorial, case study, comparison
- Length: brief (100-200 words), medium (500 words), comprehensive (1000+ words)

## 质量检查清单

生成专业指令后，检查：
- [ ] 任务目标是否清晰明确？
- [ ] 关键要求是否完整列出？
- [ ] 术语使用是否准确专业？
- [ ] 输出格式是否具体说明？
- [ ] 约束条件是否明确？
- [ ] 是否可以直接执行（不需要额外猜测）？
