# External Design Libraries

Use this file when optional external design libraries can improve the rendered HTML report without weakening information clarity or portability.

External libraries are creative references and optional implementation aids. They are not required dependencies, fixed templates, or substitutes for correct graph structure.

## React Bits

Official resources:

- Website: https://www.reactbits.dev/
- GitHub: https://github.com/DavidHDev/react-bits
- License: https://github.com/DavidHDev/react-bits/blob/main/LICENSE.md

React Bits is a library of animated, interactive, and customizable React components for text, backgrounds, and UI elements. It also provides creative tools such as Background Studio, Shape Magic, and Texture Lab.

### Appropriate Uses

Use React Bits selectively for:

- restrained title-entry or text-reveal animation
- subtle industry-relevant animated backgrounds
- gentle hover or spotlight treatment on commercial-control cards
- numeric count-up or metric-reveal effects
- restrained bottleneck pulse or emphasis
- section-entry transitions

### Inappropriate Uses

Do not use React Bits to:

- determine panoramic-graph node placement or edge routing
- replace clear arrows with decorative motion
- animate every card or node
- add cursor-following, distortion, or particle effects that reduce readability
- delay access to report content until animations complete
- make a report dependent on React when a simpler static HTML implementation is more appropriate

### Usage Rules

- Treat React Bits as optional. Use it only when the runtime supports React and the selected effect materially improves the requested style.
- For non-React HTML, study the visual principle and recreate an appropriate lightweight equivalent instead of forcing React into the report.
- Choose no more than 1-3 coherent motion patterns per report.
- Keep the panoramic industry graph readable in a fully static state.
- Ensure the report remains useful when animation is disabled.
- Support `prefers-reduced-motion` when motion is used.
- Disable or simplify animation for print and static screenshot modes.
- Avoid layout-shifting animation that changes graph geometry after load.
- Do not use dynamic effects behind dense text unless contrast remains stable.

### License Boundary

React Bits currently uses an MIT + Commons Clause license.

- Components may be used and modified as part of an application, website, or product.
- Do not sell, sublicense, or redistribute React Bits components themselves, whether individually, in a bundle, or as a ported component library.
- Do not copy the React Bits component collection into the Industry Map skill repository.
- When substantial React Bits code is used in a generated project, preserve the required copyright and license notice.

## External-Library Selection Rule

Before using any external design library, state in the non-render Render Style Brief:

- library name
- intended visual purpose
- selected effect or component family
- why it improves the report
- static and reduced-motion fallback
- relevant license or attribution requirement

If these cannot be stated clearly, do not use the library.
