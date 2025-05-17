- [ ] [[1.Hover]]
- [ ] [[2.Drag]]
- [ ] [[3.Tap]]

Framer Motion supports **gestures**, which allow you to animate components in response to user interactions such as clicks, hover, tap, drag, and focus. Gestures enhance interactivity by responding dynamically to user input, providing a more immersive experience.

Below is a detailed breakdown of the gestures Framer Motion supports:

---

## 1. **Hover Gestures**

- Trigger animations when a user hovers over a component.
- **Properties**:
    - `whileHover`: Defines the target animation values when the component is hovered over.
    - **Use Case**: Highlighting buttons or cards when the user hovers.

```jsx
<motion.div
  whileHover={{ scale: 1.2, backgroundColor: "#f00" }}
  style={{ width: 100, height: 100, backgroundColor: "#00f" }}
/>
```

---

## 2. **Tap Gestures**

- Trigger animations when a user taps or clicks on a component.
- **Properties**:
    - `whileTap`: Defines the target animation values while the user is actively tapping.
    - **Use Case**: Button press animations or visual feedback for clicks.

```jsx
<motion.div
  whileTap={{ scale: 0.9, rotate: 15 }}
  style={{ width: 100, height: 100, backgroundColor: "#00f" }}
/>
```

---

## 3. **Drag Gestures**

- Enables draggable functionality for a component.
- **Properties**:
    - `drag`: Activates drag behavior. Accepts `"x"`, `"y"`, or `true` (both axes).
    - `dragConstraints`: Restricts drag motion within specific boundaries (e.g., parent container or a bounding box).
    - `dragElastic`: Controls how elastic the drag is (0 to 1, where 0 is rigid, and 1 is very elastic).
    - `dragMomentum`: Enables or disables momentum after releasing the drag (default is `true`).
    - `onDragStart`, `onDrag`, `onDragEnd`: Event handlers for drag lifecycle.

```jsx
<motion.div
  drag="x"
  dragConstraints={{ left: -100, right: 100 }}
  dragElastic={0.2}
  style={{ width: 100, height: 100, backgroundColor: "#f00" }}
/>
```

---

## 4. **Focus Gestures**

- Trigger animations when the component gains or loses focus.
- **Properties**:
    - `whileFocus`: Defines the target animation values when the component is focused.
    - **Use Case**: Highlighting input fields or elements during keyboard navigation.

```jsx
<motion.input
  whileFocus={{ scale: 1.1, borderColor: "#f00" }}
  style={{ padding: "10px", border: "2px solid #000" }}
/>
```

---

## 5. **Key Press Gestures**

- Trigger animations when certain keys are pressed (using external logic).
- Framer Motion doesn't have a dedicated `whileKeyPress` property, but you can use event listeners in combination with `useState` and `motion`.

```jsx
import { useState } from "react";
import { motion } from "framer-motion";

const App = () => {
  const [isPressed, setIsPressed] = useState(false);

  const handleKeyDown = () => setIsPressed(true);
  const handleKeyUp = () => setIsPressed(false);

  return (
    <div
      tabIndex={0}
      onKeyDown={handleKeyDown}
      onKeyUp={handleKeyUp}
      style={{ outline: "none" }}
    >
      <motion.div
        animate={{ scale: isPressed ? 1.2 : 1 }}
        style={{ width: 100, height: 100, backgroundColor: "#00f" }}
      />
    </div>
  );
};
```

---

## 6. **Scroll Gestures**

- Trigger animations based on scroll position or visibility.
- **Properties**:
    - `useInView`: Detects whether a component is visible in the viewport.
    - **Use Case**: Animating elements as they come into view during scrolling.

```jsx
import { motion, useInView } from "framer-motion";
import { useRef } from "react";

const App = () => {
  const ref = useRef(null);
  const isInView = useInView(ref);

  return (
    <motion.div
      ref={ref}
      animate={{ opacity: isInView ? 1 : 0 }}
      transition={{ duration: 0.5 }}
      style={{ width: 100, height: 100, backgroundColor: "#00f" }}
    />
  );
};
```

---

## 7. **Combination of Gestures**

You can combine multiple gestures on the same component for more complex interactions.

```jsx
<motion.div
  whileHover={{ scale: 1.2 }}
  whileTap={{ scale: 0.9 }}
  drag
  dragConstraints={{ left: -100, right: 100 }}
  style={{ width: 100, height: 100, backgroundColor: "#0f0" }}
/>
```

---

### Gesture-Related Events

- **`onHoverStart` / `onHoverEnd`**: Triggered when a hover starts or ends.
- **`onTapStart` / `onTapEnd`**: Triggered when a tap starts or ends.
- **`onDragStart` / `onDragEnd` / `onDrag`**: Triggered during the drag lifecycle.
- **`onFocus` / `onBlur`**: Triggered when an element gains or loses focus.

---

### Best Practices

1. **Combine Gestures**: Combine `whileHover` and `whileTap` for responsive buttons.
2. **Limit Drag Bounds**: Use `dragConstraints` to ensure a smooth user experience.
3. **Optimize Performance**: Avoid overusing gestures on complex or frequently updated elements.
4. **Provide Feedback**: Gestures should provide meaningful feedback to users (e.g., visual cues on hover or drag).

By leveraging these gestures effectively, you can create rich, interactive animations tailored to user actions in your application.