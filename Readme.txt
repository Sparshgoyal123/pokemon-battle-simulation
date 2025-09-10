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
- Frontend UI built with **Vite**
- Backend powered by **MCP Server (Node.js)**

### Project Structure

### Project Structure

pokemon-battle-simulation/
├── Battle-Game/                  # Main project folder
├── dist/                         # Compiled frontend assets
├── src/                          # Source code
│   ├── web/                      # Frontend UI (Vite)
│   ├── api-bridge.js             # API bridge for backend
│   ├── package.json              # Project dependencies
│   └── ...                       # Other source files
├── .gitignore                     # Git ignore rules
├── README.md                      # Project documentation
├── package-lock.json              # npm lock file
├── package.json                   # Project metadata and dependencies
├── tsconfig.json                  # TypeScript configuration
└── update_claude_config.js        # Script to update Claude configuration

## Installation & Setup

### 1. Clone the repo
```bash
git clone https://github.com/Sparshgoyal123/pokemon-battle-simulation.git
cd pokemon-battle-game/Battle-Game
```bash 

### 2. Clone the repo
```bash

### Resources
- `resource://pokemon/data`
  - Optional params: `{ "name": string }` or `{ "id": number }`
  - Example request (MCP JSON-RPC, conceptual):
```json
{
  "method": "resources/read",
  "params": {
    "uri": "resource://pokemon/data",
    "arguments": { "name": "pikachu" }
  },
  "id": 1
}
```
  - Example response excerpt:
```json
{
  "id": 1,
  "result": {
    "id": 25,
    "name": "pikachu",
    "types": ["electric"],
    "base_stats": { "hp": 35, "attack": 55, "defense": 40, "special_attack": 50, "special_defense": 50, "speed": 90 },
    "abilities": ["static", "lightning-rod"],
    "moves": [ { "name": "thunderbolt" }, ...],
    "evolution_chain": ["pichu", "pikachu", "raichu"]
  }
}
```

If no arguments are passed, the resource returns an index of Pokémon names and a hint.

### Tools
- `simulate_battle`
  - Params: `{ "pokemonA": string, "pokemonB": string }`
  - Simulates a level-50 style, single-Pokémon battle using:
    - Type effectiveness
    - Damage formula (simplified)
    - Speed-based turn order with paralysis speed penalty
    - Status effects: paralysis (25% skip, speed halved), burn (6.25%/turn), poison (12.5%/turn)
  - Returns: participants, detailed log, and winner name or `"draw"`.

Example request (MCP JSON-RPC, conceptual):
```json
{
  "method": "tools/call",
  "params": {
    "name": "simulate_battle",
    "arguments": { "pokemonA": "charizard", "pokemonB": "blastoise" }
  },
  "id": 2
}
```

### Notes
- Uses PokeAPI live data with a 60s in-memory cache.
- Move selection prefers super effective highest-power moves among the first 30 learned moves.