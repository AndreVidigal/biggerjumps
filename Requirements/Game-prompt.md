# Build a 2D Castle Defense Game Using React + HTML5 Canvas

## 🎯 Objective

Create a playable 2D browser game where the player defends a vertical wall by throwing projectiles at approaching enemies.

The game must:

- Run in the browser
- Use React (functional components)
- Use HTML5 Canvas for all rendering
- Use JavaScript
- Not use any external game engine
- Use `requestAnimationFrame` for animation
- **All visual elements must be drawn inside a single `<canvas>` element.**

---

## 🧱 Core Game Concept

- The player controls a **soldier** positioned on top of a vertical castle wall (left side of screen).
- **Enemies** (red squares) spawn from the right and slowly move left toward the wall.
- The player presses **Enter** to throw circular projectiles in a slightly curved descending trajectory (gravity simulation).
- If a projectile hits an enemy: **both disappear**.
- **If 3 enemies reach the wall, the game ends.**

---

## 🎮 Game Elements

### 1️⃣ Player (Soldier)

- Represented as a **blue horizontal rectangle**
- Positioned on top of the wall (fixed position)
- Does not move
- Fires projectiles when user presses Enter
- **Minimum firing interval: 300ms**

### 2️⃣ Wall

- Represented as a **vertical gray rectangle**
- Positioned on the left side of the canvas
- If an enemy touches the wall:
  - Enemy disappears
  - Wall hit counter increases
  - **Game Over** when wall hit counter reaches **3**

### 3️⃣ Projectiles (Circles)

- Spawn at player position
- Shape: **black circle**
- **Physics:**
  - Constant horizontal velocity (to the right)
  - Vertical velocity affected by gravity
  - Gravity applied every frame
- Disappear when:
  - Colliding with an enemy
  - Hitting the ground (bottom of canvas)

### 4️⃣ Enemies (Squares)

- Shape: **red square**
- Spawn from the right edge of the screen
- **Spawn interval:** every 2 seconds
- Move left at constant slow speed
- Disappear if:
  - Hit by projectile
  - Reach the wall

---

## ⚙️ Physics & Collision Requirements

### Animation

- Use `requestAnimationFrame`
- Maintain consistent update loop
- **Separate:**
  - Update logic
  - Render logic

### Projectile Motion

Use simple physics:

```
vy += gravity
x += vx
y += vy
```

### Collision Detection

Implement:

- Circle vs square collision detection
- Square vs wall collision detection
- Use **mathematical** collision logic (no DOM collision).

---

## 🏗 Architecture Requirements

**Use:**

- One React component containing `<canvas>`
- `useRef` for canvas reference
- `useEffect` for:
  - Game initialization
  - Event listeners
  - Animation loop
- Store game objects in arrays:
  - `enemies[]`
  - `projectiles[]`

**Do NOT:**

- Use multiple canvas elements
- Use DOM elements for enemies or projectiles
- Use external physics engines

---

## 🎨 Visual Style

- White background
- Player: **blue**
- Enemies: **red**
- Projectiles: **black**
- Wall: **gray**
- Display wall hit counter
- Display **"Game Over"** when game ends

---

## 📦 Output Requirements

The AI must output:

- Full working React component code
- Complete CSS (if needed)
- Clear instructions to run inside a React project
- No pseudocode
- No placeholders
- **Fully playable after copy-paste**

---

## 🚀 Performance Expectations

- Smooth **60 FPS** animation
- No unnecessary re-renders
- Use canvas rendering loop instead of React state updates per frame
- Game logic stored **outside** React render cycle


## New Features - Change Requirements ##
- press "space bar" to pause the game
- replace the blue circle by @celtic.png
- position the game area down on the screen 
- Enemies should only come on the low 25% of the game area. (simulating attackers on the ground)
