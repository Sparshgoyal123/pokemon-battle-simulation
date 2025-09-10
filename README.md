## Pokemon MCP Server 

An MCP server exposing:
- Pokemon Data resource (via PokeAPI)
- Battle Simulation tool (type matchups, damage, status effects)

This project is a **Pokémon battle simulator** built using **MCP Server, Node.js, and Vite**.  
It provides both a **backend API** to simulate battles and a **frontend UI** to visualize them.

### Requirements
- Node.js 18+

### Features
- Battle simulation between two Pokémons
- Real-time updates of moves, HP, and winner
- Frontend UI built with **Vite**.
- Backend powered by **MCP Server (Node.js)**

### Project Structure

pokemon-battle-simulation/<br>
├── Battle-Game/&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp;               # Main project folder<br>
├── dist/      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;               # Compiled frontend assets<br>
├── src/                 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      &nbsp;&nbsp;   # Source code<br>
│   ├── web/            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;          # Frontend UI (Vite)<br>
│   ├── api-bridge.js        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     # API bridge for backend<br>
│   ├── package.json        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      # Project dependencies<br>
│   └── ...                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       # Other source files<br>
├── .gitignore            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;         # Git ignore rules<br>
├── README.md               &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       # Project documentation<br>
├── package-lock.json        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      # npm lock file<br>
├── package.json               &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    # Project metadata and dependencies<br>
├── tsconfig.json              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    # TypeScript configuration<br>
└── update_claude_config.js     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   # Script to update Claude configuration<br>

## Installation & Setup

### 1. Clone the repo
```bash
git clone https://github.com/Sparshgoyal123/pokemon-battle-simulation.git
cd pokemon-battle-game/Battle-Game
```

### 2. Install dependencies
```bash
npm install
```

### 3.Run the Project
- Run both backend + frontend together:
```bash
npm run ui
```

### 4. Open in browser
  Go to:
```bash
http://localhost:3002/
```

## Claude Desktop Integration
- The MCP Server is integrated with **Claude Desktop**, allowing **AI-assisted battle logic**.
- Pokemon move choices and battle outcomes are AI-driven, making each simulation dynamic and realistic.
- Backend communicates with Claude via the MCP protocol to fetch AI-powered decisions.

### Tech Stack
- **Frontend**: Vite + JavaScript
- **Backend**: Node.js + MCP Server
- **AI Integration**: Claude Desktop via MCP
- **Package Manager**: npm
  

### Notes
- Uses PokeAPI live data with a 60s in-memory cache.
- Move selection prefers super effective highest-power moves among the first 30 learned moves.
