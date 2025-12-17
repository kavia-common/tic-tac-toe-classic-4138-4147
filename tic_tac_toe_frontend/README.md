# Tic Tac Toe Frontend (React)

## Overview
This is the React frontend for a classic Tic Tac Toe game. It presents a modern, minimalistic UI that allows two players to play on a 3×3 grid, with live status updates for turns, win and draw detection, and a restart option.

- Workspace: tic-tac-toe-classic-4138-4147
- Container: tic_tac_toe_frontend (web, React, port 3000)
- UI Layout: Centered vertical stack with status above the board and restart control below
- Style Theme: Light, minimalistic with #3b82f6 and #06b6d4 accents

For full product scope and design decisions, see:
- docs/PRD.md
- docs/ARCHITECTURE.md

## Features
- Game board display (3×3 grid)
- Player turn management (X and O)
- Win detection (rows, columns, diagonals)
- Draw detection (board full, no winner)
- Restart game (reset all state)

## Tech Stack
- Framework: React
- Platform: Web (SPA)
- Language: JavaScript/TypeScript (depending on setup)
- Styling: Minimalistic light theme (implementation-specific; CSS Modules or similar)

## Getting Started

### Prerequisites
- Node.js (LTS recommended) and npm or yarn

### Installation
1. Navigate to the container directory:
   - cd tic-tac-toe-classic-4138-4147/tic_tac_toe_frontend
2. Install dependencies:
   - npm install
   or
   - yarn install

### Environment Variables
This app can be configured via environment variables. Create a .env file in tic_tac_toe_frontend with any of the following (all optional for local play):

- REACT_APP_API_BASE
- REACT_APP_BACKEND_URL
- REACT_APP_FRONTEND_URL
- REACT_APP_WS_URL
- REACT_APP_NODE_ENV
- REACT_APP_NEXT_TELEMETRY_DISABLED
- REACT_APP_ENABLE_SOURCE_MAPS
- REACT_APP_PORT
- REACT_APP_TRUST_PROXY
- REACT_APP_LOG_LEVEL
- REACT_APP_HEALTHCHECK_PATH
- REACT_APP_FEATURE_FLAGS
- REACT_APP_EXPERIMENTS_ENABLED

Example .env:
REACT_APP_NODE_ENV=development
REACT_APP_ENABLE_SOURCE_MAPS=true
REACT_APP_LOG_LEVEL=info
REACT_APP_FEATURE_FLAGS={}
REACT_APP_EXPERIMENTS_ENABLED=false

Notes:
- Prefix REACT_APP_ is required for variables to be exposed to the browser in CRA-like setups.
- Variables are optional for the base game and focus on future integrations, logging, and feature flags.

### Available Scripts
Common scripts (your package.json may vary by tooling):
- npm start or yarn start
  - Runs the development server on port 3000 with hot reload.
- npm run build or yarn build
  - Produces a production build in the build/ folder.
- npm test or yarn test
  - Runs unit and component tests where configured.

## Running Locally (Preview)
1. Ensure dependencies are installed and .env is set if needed.
2. Start the dev server:
   - npm start
   or
   - yarn start
3. Open http://localhost:3000 in your browser.

Tip: If a preview system is present in your environment (e.g., containerized preview or CI preview URLs), ensure REACT_APP_FRONTEND_URL is set accordingly and consult your platform’s preview instructions.

## Project Structure (Suggested)
Actual structure may vary depending on scaffolding. A simple approach is:
- src/
  - components/
    - Game.jsx
    - Board.jsx
    - Square.jsx
    - StatusBanner.jsx
    - RestartButton.jsx
  - utils/
    - gameLogic.js
  - App.jsx
  - index.jsx
- public/
- package.json

See docs/ARCHITECTURE.md for an in-depth explanation of the component responsibilities, state management, data flow, and styling notes.

## Styling and Accessibility
- Theme:
  - Background: #f9fafb
  - Surface: #ffffff
  - Text: #111827
  - Primary Accent: #3b82f6
  - Success/Accent: #06b6d4
- Accessibility:
  - Use button semantics for squares with appropriate ARIA attributes.
  - Provide visible focus states and support keyboard navigation.
  - Announce status changes (turn, win, draw) via aria-live or role="status".

## Testing
- Unit tests for core game logic (win/draw detection).
- Component tests for Game interactions, including restart.
- Consider basic a11y checks (e.g., jest-axe) for CI.

## Build & Deployment
- Build:
  - npm run build or yarn build
- Deploy options:
  - Static hosting (Netlify, Vercel, GitHub Pages, S3) or a container-based approach.
- Observability:
  - Gate console logs by REACT_APP_LOG_LEVEL.
  - Feature-flag any analytics or error reporting.
- Healthchecks:
  - REACT_APP_HEALTHCHECK_PATH can be used to expose a simple route or static file for liveness checks, if desired.

## Troubleshooting
- Port conflicts:
  - Ensure port 3000 is free or configure accordingly.
- Missing env variables:
  - All variables are optional; if used, ensure they start with REACT_APP_.
- Build source maps:
  - Control via REACT_APP_ENABLE_SOURCE_MAPS.
- Telemetry/analytics (if added):
  - Toggled via REACT_APP_NEXT_TELEMETRY_DISABLED or feature flags.

## Roadmap
- Optional: Winning line highlight
- Optional: AI opponent mode
- Optional: Online multiplayer via WebSockets
- Optional: Persist game history locally

## References
- docs/PRD.md – Product requirements and acceptance criteria
- docs/ARCHITECTURE.md – Architecture, component structure, game logic, and data flow
