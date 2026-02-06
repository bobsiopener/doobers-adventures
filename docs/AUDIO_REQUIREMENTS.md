# Audio Requirements for Doober's Adventures

This document outlines all sound effects and music needed for the game.

## Sound Effects

### Doober Sounds
| Sound | Description | Notes |
|-------|-------------|-------|
| `doober-footstep.wav` | Light paw tapping sound | Soft, quick - play 4x per walk cycle |
| `doober-run.wav` | Faster paw sounds | Quicker tempo than walking |
| `doober-bark.wav` | Happy/excited bark | Short, playful |
| `doober-whimper.wav` | Sad sound when caught | Brief, pitiful |
| `doober-pant.wav` | Panting after running | Loopable |

### Mischief Action Sounds
| Sound | Trigger | Description |
|-------|---------|-------------|
| `mischief-trash.wav` | Knocking over trash | Crash + clatter |
| `mischief-food.wav` | Eating food | Chomping/munching |
| `mischief-shoes.wav` | Chewing shoes | Squeaky chewing |
| `mischief-plant.wav` | Digging in plants | Dirt scattering |
| `mischief-couch.wav` | Jumping on couch | Boing/springs |
| `mischief-generic.wav` | Any mischief | Brief chaos sound |
| `points-gained.wav` | Points earned | Positive ding/chime |

### Owner Sounds
| Sound | Description | Notes |
|-------|-------------|-------|
| `owner-footstep.wav` | Normal walking | Heavier than Doober |
| `owner-footstep-angry.wav` | Searching/angry | Faster, heavier stomping |
| `owner-spot.wav` | Owner spots Doober | Alert sound/gasp |
| `owner-calm.wav` | Anger subsides | Relieved sigh |

### UI Sounds
| Sound | Trigger | Description |
|-------|---------|-------------|
| `meter-tick.wav` | Mischief meter increases | Soft tick/blip |
| `meter-full.wav` | Mischief meter maxes | Warning chime |
| `anger-tick.wav` | Anger meter decreases | Soft tick |
| `phase-change.wav` | Phase transitions | Whoosh/transition |
| `button-click.wav` | Menu button press | Soft click |
| `button-hover.wav` | Menu button hover | Subtle sound |

### Game State Sounds
| Sound | Trigger | Description |
|-------|---------|-------------|
| `game-start.wav` | Game begins | Cheerful start |
| `caught-alarm.wav` | Doober is caught | Dramatic sting |
| `win-fanfare.wav` | Victory achieved | Celebratory jingle |
| `hide-success.wav` | Successfully hidden | Relief sound |

## Music Tracks

### Main Theme
- **File:** `music-main.ogg` (or `.mp3`)
- **Style:** Cozy, playful, mischievous
- **Tempo:** Moderate (120-130 BPM)
- **Instruments:** Pizzicato strings, light percussion, xylophone
- **Mood:** Stardew Valley meets Tom & Jerry
- **Duration:** 2-3 minutes, loopable
- **Notes:** Should feel like sneaking around the house having fun

### Tension/Hide Phase Music
- **File:** `music-tension.ogg`
- **Style:** Suspenseful but still playful
- **Tempo:** Slightly faster (130-140 BPM)
- **Instruments:** Staccato strings, ticking percussion
- **Mood:** Comedic tension, hide and seek
- **Duration:** 1-2 minutes, loopable
- **Notes:** Transitions smoothly from main theme

### Victory Jingle
- **File:** `music-victory.ogg`
- **Style:** Celebratory, triumphant
- **Duration:** 5-10 seconds
- **Notes:** Play once on win

### Game Over Sting
- **File:** `music-gameover.ogg`
- **Style:** Comedic failure, "wah wah"
- **Duration:** 3-5 seconds
- **Notes:** Should be funny, not sad

## Recommended Sources

### Free/Royalty-Free
1. **Freesound.org** - CC licensed sound effects
2. **OpenGameArt.org** - Game-specific assets
3. **Pixabay** - Royalty-free sounds
4. **Zapsplat** - Free with attribution

### Paid Asset Stores
1. **Humble Bundle** - Occasional game audio packs
2. **Unity Asset Store** - Game-ready audio
3. **Itch.io** - Indie game assets
4. **GameDev Market** - Affordable packs

### AI Generation
1. **Suno** - AI music generation
2. **Udio** - AI music generation
3. **ElevenLabs Sound Effects** - AI SFX (coming soon)

## Implementation Notes

### Audio System Requirements
```javascript
// Suggested audio manager structure
const audio = {
  sfx: {
    // Sound effects loaded as Audio objects
    // Short, fire-and-forget
  },
  music: {
    // Background tracks
    // Need crossfade between phases
  },
  settings: {
    masterVolume: 1.0,
    sfxVolume: 0.8,
    musicVolume: 0.6,
    muted: false
  }
};
```

### Volume Recommendations
- **SFX:** 80% of master
- **Music:** 50-60% of master (should be background)
- **Important alerts:** 100% of master

### File Formats
- **SFX:** `.wav` (web-compatible) or `.ogg`
- **Music:** `.ogg` (smaller) or `.mp3` (wider support)
- **Fallback:** Provide both formats for browser compatibility

## Priority Order

### Phase 1 (Essential)
1. Doober footsteps
2. Mischief generic sound
3. Phase change sound
4. Caught alarm
5. Win fanfare

### Phase 2 (Important)
1. Main theme music
2. Tension music
3. Owner footsteps
4. Points gained sound

### Phase 3 (Polish)
1. All specific mischief sounds
2. UI sounds
3. Additional Doober vocalizations
4. Music crossfades
