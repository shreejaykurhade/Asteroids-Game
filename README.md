# Asteroids Game

A classic Asteroids arcade game implementation built with HTML5 Canvas and JavaScript. Navigate your spaceship through an asteroid field, shooting asteroids to clear each level while avoiding collisions.

## Features

- **Classic Gameplay**: Faithful recreation of the original Asteroids arcade experience
- **Progressive Difficulty**: Levels increase in difficulty with more asteroids and faster speeds
- **Physics Simulation**: Realistic momentum, friction, and wraparound screen edges
- **Audio System**: Dynamic music tempo and sound effects (requires audio files)
- **Responsive Design**: Automatically scales to fill the browser window
- **Score System**: Points awarded for destroying asteroids, with local high score storage
- **Visual Effects**: Ship explosions, laser impacts, and thruster flames

## How to Play

### Controls
- **↑ Arrow Key**: Thrust forward
- **← Arrow Key**: Rotate left
- **→ Arrow Key**: Rotate right  
- **Spacebar**: Fire laser

### Objective
- Destroy all asteroids to advance to the next level
- Avoid colliding with asteroids
- Survive as long as possible to achieve a high score

### Scoring
- **Large Asteroid**: 20 points
- **Medium Asteroid**: 50 points  
- **Small Asteroid**: 100 points

## Game Mechanics

### Ship Physics
- **Momentum**: Ship maintains velocity when not thrusting
- **Friction**: Gradual slowdown when thrust is not applied
- **Screen Wrap**: Ship and projectiles wrap around screen edges
- **Invincibility**: Brief invincibility period after respawn with visual blinking

### Asteroids
- **Splitting**: Large asteroids split into 2 medium, medium split into 2 small
- **Random Generation**: Each asteroid has unique shape and movement pattern
- **Collision Detection**: Circular collision boundaries for accurate hit detection

### Weapons
- **Laser Limit**: Maximum 10 lasers on screen simultaneously
- **Travel Distance**: Lasers automatically expire after traveling 60% of screen width
- **Explosion Effects**: Visual feedback when lasers hit asteroids

## Setup Instructions

### Basic Setup
1. Save the HTML file (e.g., `asteroids.html`)
2. Open in any modern web browser
3. Game will run immediately (without audio)

### Full Setup with Audio
1. Create a `sounds/` folder in the same directory as the HTML file
2. Add the following audio files:
   - `explode.m4a` - Ship explosion sound
   - `hit.m4a` - Asteroid hit sound  
   - `laser.m4a` - Laser firing sound
   - `thrust.m4a` - Ship thruster sound
   - `music-low.m4a` - Background music (low tempo)
   - `music-high.m4a` - Background music (high tempo)

### Directory Structure
```
asteroids.html
sounds/
├── explode.m4a
├── hit.m4a
├── laser.m4a
├── thrust.m4a
├── music-low.m4a
└── music-high.m4a
```

## Configuration

### Game Constants (Customizable)
```javascript
const FPS = 30;                    // Frame rate
const GAME_LIVES = 3;              // Starting lives
const ROID_NUM = 3;                // Starting asteroid count
const SHIP_SIZE = 30;              // Ship size in pixels
const LASER_MAX = 10;              // Max simultaneous lasers
const LASER_SPD = 500;             // Laser speed (pixels/second)
const SHIP_THRUST = 5;             // Ship acceleration
const SHIP_TURN_SPD = 360;         // Turn speed (degrees/second)
const FRICTION = 0.7;              // Space friction coefficient
```

### Debug Options
```javascript
const SHOW_BOUNDING = false;       // Show collision circles
const SHOW_CENTRE_DOT = false;     // Show ship center point
const MUSIC_ON = true;             // Enable background music
const SOUND_ON = true;             // Enable sound effects
```

## Technical Implementation

### Canvas Rendering
- **2D Context**: Uses HTML5 Canvas 2D rendering context
- **Responsive Sizing**: Canvas automatically resizes to viewport
- **Vector Graphics**: All game objects drawn with vector paths

### Game Loop
- **Fixed Timestep**: 30 FPS update cycle using `setInterval`
- **Separation of Concerns**: Update logic separate from rendering
- **State Management**: Game state tracked through global variables

### Audio System
- **Multiple Streams**: Supports overlapping sound effects
- **Dynamic Music**: Tempo adjusts based on remaining asteroids
- **Volume Control**: Configurable audio levels

## Browser Compatibility

- **Modern Browsers**: Works in all browsers supporting HTML5 Canvas
- **Mobile Support**: Touch controls not implemented (keyboard required)
- **Local Storage**: Uses localStorage for high score persistence

## File Dependencies

### Required Files
- Main HTML file (self-contained)

### Optional Files (for audio)
- 6 audio files in M4A format (see setup instructions)

## Performance Notes

- **Lightweight**: Pure JavaScript implementation with no external libraries
- **Optimized Rendering**: Efficient canvas drawing operations
- **Memory Management**: Objects cleaned up when destroyed
- **Smooth Animation**: Consistent 30 FPS performance

## Customization Ideas

### Visual Modifications
- Change ship design by modifying `drawShip()` function
- Adjust asteroid appearance in the asteroid rendering section
- Modify explosion effects and colors

### Gameplay Tweaks
- Adjust difficulty progression by changing level multipliers
- Modify scoring system in `destroyAsteroid()` function
- Change physics parameters (thrust, friction, speeds)

### Audio Enhancements
- Add more sound effects for different events
- Implement spatial audio based on object positions
- Create dynamic music mixing

## Known Limitations

- No mobile touch controls
- Audio requires external files
- Single-player only
- No power-ups or special weapons
- Fixed visual style (no themes)
