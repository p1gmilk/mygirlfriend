# Valentine's Music Box - Project Specification

## Project Overview
A web-based interactive Valentine's gift that displays a collection of 7-8 special musical memories, each paired with personal messages and optional visual elements, plus an AI-powered Future Memory Generator. The interface resembles a digital jewelry box or collection of floating musical notes/cards that reveal their contents when clicked.

## Core Features
1. Interactive Memory Cards
   - 7-8 clickable elements representing different memories
   - Each card contains:
     - Embedded MP3 audio player with song snippet
     - Personal message
     - Multiple videos/photos
   - Smooth open/close animations
   - Visible indication of unplayed/played status

2. Future Memory Generator
   - Special interactive card for generating imagined future moments
   - Text input for memory prompts
   - LLM-powered memory generation
   - Elegant display of generated memories
   - Option to save favorite generated memories
   - Loading states and error handling
   - Background music that matches the generated memory's mood

3. Visual Design
   - Flowery, romantic aesthetic
   - Floating/arranged cards in an artful layout
   - Soft color palette (suggested: rose golds, soft pinks, warm whites)
   - Elegant typography for messages
   - Simple but beautiful animations

4. Audio Integration
   - Custom HTML5 audio player
   - MP3 file integration
   - Play/pause functionality
   - Progress bar
   - Volume control
   - Smooth transitions between songs

## Technical Stack
- Frontend: React
- Styling: Tailwind CSS
- Animation: CSS transitions/animations
- Audio: HTML5 Audio API
- Backend: Python (FastAPI/Flask) for LLM integration
- Deployment: GitHub Pages/Vercel (frontend), Personal server (LLM backend)

## Project Structure
```
src/
  components/
    MemoryCard.jsx        # Individual memory card component
    AudioPlayer.jsx       # Custom audio player component
    FutureMemory.jsx      # Future memory generator component
    MusicBox.jsx          # Main container component
  data/
    memories.js           # Array of memory objects
  styles/
    animations.css        # Custom animations
  App.jsx                # Root component

server/
  app.py                 # FastAPI/Flask server
  prompt_template.py     # LLM prompt templates
  requirements.txt       # Python dependencies
```

## Data Structures
```javascript
// Memory object structure
{
  id: 1,
  title: "Our First Concert",
  message: "Remember when we...",
  audioUrl: "/audio/concert-snippet.mp3",
  imageUrl: "/images/concert.jpg",
  color: "#FFE4E1"  // Optional: unique card color
}

// Future memory request/response
{
  prompt: "Our dream vacation in Paris",
  memory: "We're standing at the top of the Eiffel Tower...",
  timestamp: "2024-02-14T12:00:00Z",
  mood: "romantic"  // For music selection
}
```

## Development Phases
1. Setup & Basic Structure (Day 1)
   - Create React project
   - Set up Tailwind
   - Basic component structure

2. Core Functionality (Days 2-3)
   - Implement memory cards
   - Build custom audio player
   - Add click interactions
   - Basic animations

3. Audio Integration (Day 4)
   - Implement audio player
   - Add MP3 handling
   - Create audio snippets

4. Future Memory Generator (Day 5)
   - Set up backend server
   - Implement LLM integration
   - Create frontend component
   - Add save functionality

5. Content & Polish (Days 6-7)
   - Add all memories/content
   - Refine animations
   - Style improvements
   - Testing & fixes

## Backend API Endpoints
```python
POST /api/generate-memory
Request:
{
    "prompt": str,        # User input
    "mood": str          # Optional mood for music
}
Response:
{
    "memory": str,       # Generated memory
    "mood": str,         # Suggested mood
    "success": bool      # Status
}
```

## Content Preparation Needed
- 7-8 special songs (MP3 snippets)
- Personal messages for each memory
- Optional: photos or visual elements
- Color scheme preferences
- Any specific fonts or styling preferences
- LLM prompt templates

## Nice-to-Have Features (Time Permitting)
- Particle effects when cards open
- Background music
- Progressive reveal option
- Custom card shapes/designs
- Message typing animation
- AI-generated art for future memories
- Mood-based color themes
- Export/share generated memories

## Accessibility Considerations
- Keyboard navigation
- Screen reader compatibility
- Appropriate color contrast
- Pause/stop animation option
- Clear focus indicators
- Audio controls
- Loading states and error messages

## LLM Integration Notes
- Use temperature setting of 0.7 for creative but controlled outputs
- Implement content filtering for appropriate responses
- Keep response length consistent (2-3 sentences)
- Include error handling and fallback responses
- Consider rate limiting for the generation feature

This specification provides a foundation for the project while remaining flexible enough to accommodate changes during development. The focus is on creating a meaningful, personal experience while keeping the technical implementation achievable within the 7-day timeframe.
