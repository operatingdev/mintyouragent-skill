# MintYourAgent CLI

A pure Python CLI for launching tokens on Solana via [pump.fun](https://pump.fun). No bash, no jq, no solana-cli needed.

🌐 **Website:** [mintyouragent.com](https://www.mintyouragent.com)  
📖 **Docs:** [mintyouragent.com/for-agents](https://www.mintyouragent.com/for-agents)

## Features

- 🐍 **Pure Python** — Works on Windows, Mac, Linux
- 🔐 **Local Signing** — Private keys never leave your machine
- 💰 **Keep 100%** — You keep all pump.fun creator fees
- 🤖 **AI-First** — Built for autonomous agents (JSON output, no prompts)

## Installation

### Via ClawdHub (recommended for AI agents)
```bash
clawdhub install mintyouragent
```

### Manual Installation
```bash
# Clone repo
git clone https://github.com/operatingdev/mintyouragent-skill.git
cd mintyouragent-skill

# Install dependencies
pip install solders requests
```

## Quick Start

```bash
# Create wallet
python mya.py setup

# Check balance
python mya.py wallet balance

# Launch a token
python mya.py launch \
  --name "My Token" \
  --symbol "MYT" \
  --description "The best token" \
  --image "https://example.com/image.png"
```

## Commands

| Command | Alias | Description |
|---------|-------|-------------|
| `setup` | `s` | Create a new wallet |
| `wallet` | `w` | Wallet management |
| `launch` | `l` | Launch a token |
| `tokens` | `t` | List tokens in wallet |
| `history` | `h` | Show command history |
| `backup` | `b` | Backup/restore wallet |
| `status` | `st` | Check API/RPC status |
| `trending` | `tr` | Show trending tokens |
| `leaderboard` | `lb` | Show launch leaderboard |
| `config` | `c` | Manage configuration |

## Launch Parameters

| Param | Required | Description |
|-------|----------|-------------|
| `--name` | ✅ | Token name (max 32 chars) |
| `--symbol` | ✅ | Ticker (max 10 chars, ASCII only) |
| `--description` | ✅ | Token description |
| `--image` | ✅ | Image URL (HTTPS) |
| `--initial-buy` | ❌ | Initial buy in SOL |
| `--twitter` | ❌ | Twitter/X link |
| `--telegram` | ❌ | Telegram link |
| `--website` | ❌ | Website link |
| `--dry-run` | ❌ | Test without launching |

## Wallet Storage

Your wallet is stored in `~/.mintyouragent/` (your home directory):

```
~/.mintyouragent/
├── wallet.json      # Wallet with checksum
├── config.json      # Configuration
├── RECOVERY_KEY.txt # Backup signing key
├── audit.log        # Action log
└── backups/         # Wallet backups
```

⚠️ **Important:** Wallet is stored separately from the skill folder — safe during updates.

## Rate Limits

| Tier | Daily Launches |
|------|---------------|
| Free | 3 |
| With $SOUL | +1 per 10 $SOUL held |

## Security

- All signing happens **locally** on your machine
- Private keys are **never transmitted** to any server
- Only signed transactions and public addresses are sent
- Source code is MIT licensed and open for audit

## License

MIT License — see [LICENSE](LICENSE)

## Links

- 🌐 [Website](https://www.mintyouragent.com)
- 📖 [Documentation](https://www.mintyouragent.com/for-agents)
- 🐦 [Twitter](https://x.com/mintyouragent)
