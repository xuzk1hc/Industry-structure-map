# Render Style Brief

Use this file when preparing the non-render visual direction for the HTML consulting infographic.

The style brief must guide creative rendering without prescribing a fixed HTML template, component system, or machine schema.

## Required Style Brief

Include this non-render section in the Markdown source:

```markdown
## Non-Render: Render Style Brief

### Style Profile
[Named profile or custom direction]

### Visual Character
[3-6 adjectives describing the intended feeling]

### Domain Signals
[Visual cues that make the design feel specific to the mapped industry]

### Information Hierarchy
1. [Primary visual block]
2. [Secondary visual block]
3. [Supporting visual blocks]

### Color Direction
[Dominant, supporting, emphasis, bottleneck, and uncertainty colors]

### Typography Direction
[Display and body-text character; density and hierarchy]

### Graph Language
[Node, arrow, route, bottleneck, company-badge, and lane behavior]

### Creative Freedom
[What the renderer may reinterpret or invent]

### Hard Restrictions
[Non-negotiable content, layout, and legibility rules]

### Reference Assets
[Attached images, local assets, or named references to study]

### Optional External Design Libraries
[Library, intended effect, reason, static/reduced-motion fallback, and license note]

### Anti-References
[Visual patterns or prior failures to avoid]
```

Do not render the style brief as visible report content.

## Writing Rules

- Describe the desired visual result with concrete design language, not vague words such as `premium`, `beautiful`, or `modern`.
- Explain visual hierarchy, density, contrast, graph behavior, and domain-specific signals.
- State what may vary so the renderer retains creative freedom.
- State hard restrictions separately from preferences.
- Treat reference images as design evidence, not as templates to copy literally.
- Treat external design libraries as optional. Name the intended effect and fallback instead of broadly asking the renderer to use the entire library.
- Prefer one coherent style direction over mixing several unrelated aesthetics.

## Example: Chip-Tech Blue

```markdown
### Style Profile
Chip-Tech Blue

### Visual Character
克制、精密、冷静、高信息密度、具有芯片制造与高速数据流动感。

### Domain Signals
使用晶圆、封装层、光路、电路走线、测试节点等抽象视觉语言；避免通用 SaaS 仪表盘感。

### Information Hierarchy
1. 产业全景图
2. 产品形成流程
3. 商业控制点
4. 瓶颈热力排名

### Color Direction
深蓝背景；冰蓝和青色用于主链；橙色用于替代路线；红色只用于关键瓶颈；灰蓝用于弱关系。

### Graph Language
产品形成关系使用清晰实线箭头；商业、认证和替代关系使用虚线；上市公司使用小型 logo + ticker badge。

### Creative Freedom
允许自由设计节点形状、背景纹理、微动效、具体排版和 SVG 表现方式。

### Optional External Design Libraries
React Bits may be used for one restrained background or title-entry effect when React is appropriate. Keep a static fallback and disable or simplify motion for print.

### Hard Restrictions
禁止首屏长解释；禁止连线遮挡文字和徽章；禁止渲染生产数据表；产品形成流程紧跟全景图。
```

## Creative-Freedom Boundary

The renderer may freely choose:

- SVG, Canvas, HTML/CSS, or a mixed implementation
- node shapes and internal composition
- background texture and restrained motion
- typography pairing
- exact layout geometry
- responsive behavior
- decorative visual details that support the domain

The renderer may not reinterpret:

- visible-section allowlist and denylist
- industry relationships and edge direction
- claim-state meaning
- bottleneck heat meaning
- company listing status or ticker
- required ordering of the panoramic map and product-formation flow
- legibility requirements
