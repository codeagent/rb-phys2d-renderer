[![CI](https://github.com/codeagent/rb-phys2d-renderer/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/codeagent/rb-phys2d-renderer/actions/workflows/ci.yml) [![npm version](https://badge.fury.io/js/rb-phys2d-renderer.svg)](https://badge.fury.io/js/rb-phys2d-renderer)

# Debug Renderer For RbPhys2D

The means for visualizing and interacting with world created by [RbPhys2D](https://github.com/codeagent/rb-phys2d)

## What's Included:

- Picking And Dragigin Objects (`LMB`)
- Viewport Scaling And Navigation (`WHEEL`, `MMB`)
- Rendering `Axes`, `Objects`, `Joints`, `Contacts`
- Touch Devices Support

## Installation

Using `npm` package manager:

```bash
npm install rb-phys2d-renderer
```

## Usage

### ESM

```typescript
import { createViewport, createWorldRenderer } from 'rb-phys2d-renderer';

const canvas = document.getElementById('canvas');

// Create Viewport And Assign Required Controls
const viewport = createViewport(canvas)
  .addMousePickingControl(world)
  .addViewportAdjustingControl();

const renderer = createWorldRenderer(viewport, world);

// Somewhere in loop:

// clear viewport
renderer.clear();

// render parts determined by render mask
renderer.render(RenderMask.Default & ~RenderMask.Joint);
```

### Browser

```html
<!-- include bundle  -->
<script src="./node_modules/rb-phys2d-renderer/dist/bundle/rb-phys2d-renderer.js"></script>

<script>
  // use global accessible object rbPhys2dRenderer
  const viewport = rbPhys2dRenderer
    .createViewport(canvas)
    .addMousePickingControl(world)
    .addViewportAdjustingControl();

  const renderer = rbPhys2dRenderer.createWorldRenderer(viewport, world);

  // ...

  renderer.clear();
  renderer.render(
    rbPhys2dRenderer.RenderMask.Default & ~rbPhys2dRenderer.RenderMask.Joint
  );
</script>
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
