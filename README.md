# ◈ EngageChain

> **AI-powered opinion and validation Intelligent Contract on GenLayer.**  
> User submits text → AI evaluates → validators reach consensus → result is stored on-chain.

---

## What is EngageChain?

EngageChain is an [Intelligent Contract](https://docs.genlayer.com/intelligent-contracts/overview) built on GenLayer that transforms subjective opinions into verifiable on-chain verdicts through AI and decentralized consensus.

---

## Protocol Flow

1. **Human Input** — the user submits an opinion, proposal, or dispute  
2. **AI Evaluation** — the contract calls an LLM via `gl.exec_prompt()` to analyze the text  
3. **Optimistic Democracy** — validators execute the same prompt and compare results using the *Equivalence Principle*  
4. **On-Chain Record** — the consensus verdict is stored permanently and immutably  

---

## Project Structure
engagechain/
├── contract/
│ └── engagechain.py
├── frontend/
│ ├── index.html
│ ├── app.js
│ └── styles.css
└── README.md

---

## Contract: `contract/engagechain.py`

Written in Python using the GenLayer SDK.

### Persistent State

- `submissions` → original user text  
- `ai_responses` → AI-generated responses  
- `verdicts` → final consensus result  
- `authors` → user addresses  
- `statuses` → pending / evaluated / finalized  
- `timestamps` → logical block reference  
- `total_submissions` → global counter  

---

## Core Functions

- `submit_opinion(text)` → create new entry  
- `evaluate_opinion(id)` → run AI evaluation  
- `store_ai_response(id, response)` → save external AI response  
- `finalize_opinion(id, verdict)` → finalize result  
- `get_full_entry(id)` → return all data  

---

## Deployment

### GenLayer Studio (Recommended)

1. Go to https://studio.genlayer.com  
2. Paste `contract/engagechain.py`  
3. Deploy  
4. Copy contract address into frontend  

---

## Frontend

Simple static UI using GenLayerJS.

### Setup

1. Open `frontend/index.html`  
2. Configure:
   - Contract Address  
   - RPC Endpoint  
   - Private Key (testnet only)  
   - Account Address  
3. Save config  
4. Submit an opinion  

### CDN

```html
<script src="https://unpkg.com/genlayer@latest/dist/genlayer.umd.js"></script>
