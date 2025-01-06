# ImgStack

A React component for creating beautiful, interactive image stacks with configurable aspect ratios and responsive behavior.

## Demo

<div align="center" style="max-width: 800px; margin: 0 auto;">
  <div style="position:relative; width:100%; height:0px; padding-bottom:87.775%">
    <iframe 
      allow="fullscreen" 
      allowfullscreen 
      height="100%" 
      src="https://streamable.com/e/ysooug?" 
      width="100%" 
      style="border:none; width:100%; height:100%; position:absolute; left:0px; top:0px; overflow:hidden;">
    </iframe>
  </div>
</div>

### Demo Features

- 🖱️ Hover over the stack to see the caption and animation effects
- 🔍 Click to open the full-size image gallery
- ⌨️ Press `Esc`, click outside, or use the close button to dismiss the dialog
- 📱 Fully responsive and mobile-friendly

## Features

- 🖼️ Stacked image presentation with hover effects
- 📐 Configurable aspect ratios (predefined or custom)
- 📱 Responsive design with mobile-first approach
- 🎭 Dark mode support
- 🔍 Modal view for full-size images
- ✨ Smooth animations and transitions
- ♿ Accessibility-friendly

## Installation

```bash
npm install img-stacks
```

---

## Usage

```tsx
import { ImgStack } from "img-stacks";

function MyComponent() {
  const images = [
    {
      src: "path/to/image1.jpg",
      alt: "Description of image 1",
      caption: "Caption for image 1",
    },
    {
      src: "path/to/image2.jpg",
      alt: "Description of image 2",
      caption: "Caption for image 2",
    },
  ];

  return (
    <ImgStack
      images={images}
      size={{ type: "aspect-ratio", width: 400, ratio: "wide" }}
    />
  );
}
```

## Configuration

### Image Configuration

Each image in the stack requires the following properties:

```typescript
interface StackImage {
  src: string; // URL of the image
  alt: string; // Alt text for accessibility
  caption: string; // Caption shown in the dialog view
}
```

### Size Configuration

The component supports two types of size configuration:

#### 1. Aspect Ratio

```typescript
{
  type: "aspect-ratio";
  width: number; // Desired width in pixels
  ratio: AspectRatio; // Predefined ratio or custom number
}
```

Predefined aspect ratios:

- `"square"` (1:1)
- `"landscape"` (4:3)
- `"wide"` (16:9)
- `"ultrawide"` (21:9)
- `"portrait"` (3:4)
- `"tall"` (9:16)

Or use a custom numeric ratio (e.g., 2.35 for cinemascope).

#### 2. Fixed Size

```typescript
{
  type: "fixed";
  width: number; // Width in pixels
  height: number; // Height in pixels
}
```

### Responsive Behavior

The component is inherently responsive:

- Uses the specified width as a maximum
- Automatically scales down on smaller screens
- Maintains aspect ratio at all sizes
- No horizontal scrollbars

## Examples

### Default (Responsive)

```tsx
<ImgStack images={images} />
```

### Square Aspect Ratio

```tsx
<ImgStack
  images={images}
  size={{ type: "aspect-ratio", width: 300, ratio: "square" }}
/>
```

### Custom Aspect Ratio (Cinemascope)

```tsx
<ImgStack
  images={images}
  size={{ type: "aspect-ratio", width: 400, ratio: 2.35 }}
/>
```

### Fixed Size

```tsx
<ImgStack images={images} size={{ type: "fixed", width: 400, height: 300 }} />
```

## Best Practices

1. Use same-size images for best visual results
2. Provide meaningful alt text for accessibility
3. Keep image stacks to 3-5 images for optimal performance
4. Use aspect ratios that match your content type
5. Consider mobile users when setting widths

## License

MIT
