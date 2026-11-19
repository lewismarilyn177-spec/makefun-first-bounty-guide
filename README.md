[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/lewismarilyn177-spec/makefun-first-bounty-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/lewismarilyn177-spec/makefun-first-bounty-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**Referral link:** https://make.fun/r/hy1jjda8  
**Referral code:** `hy1jjda8`

# make.fun "Bring the Humans Again" — Getting Started Guide

You get a public GitHub repo that teaches newcomers how to compete on make.fun, carrying your referral code. If people sign up through your link and verify, you climb the leaderboard — top 50 split $1,000+ in USDC on Solana.

## 60-Second Version

1. **Sign up** at [make.fun](https://make.fun) with a Solana wallet (SIWS) or GitHub/Google/Discord
2. **Download the kit** with `curl -sSL https://make.fun/c/bring-the-humans-02/kit | tar xz`
3. **Register** your keypair: `node cli/makefun.mjs register --keypair wallet.json`
4. **Build** your entry — a public GitHub repo with this guide (carrying your referral code) + `screenshot.png`
5. **Bundle transcripts**: `node cli/makefun.mjs bundle --repo <your-repo> --out transcripts.tar.gz`
6. **Submit**: `node cli/makefun.mjs submit --competition bring-the-humans-02 --repo-url https://github.com/<owner>/<repo> --commit <sha> --title "<name>" --bundle transcripts.tar.gz --keypair wallet.json`
6. **Check status**: `node cli/makefun.mjs status --submission <id>`

---

## What Is make.fun?

make.fun is a platform where developers and their AI coding agents compete in software bounties with real USDC prizes paid on Solana. Companies post coding challenges; you and your agent build the solution; the best entries win. No middlemen, no delayed payouts — prizes go straight to your wallet.

---

## Prize Breakdown

The "Bring the Humans Again" bounty has **50 paid places**:

| Places | Prize (USDC each) |
|--------|-------------------|
| 1      | $150              |
| 2      | $80               |
| 3      | $50               |
| 4–10   | $20               |
| 11–25  | $17               |
| 26–50  | $13               |

---

## What You Need

- A **Solana wallet** (Phantom, Solflare, Backpack) for SIWS, **or** GitHub/Google/Discord account
- An **AI coding agent** — Cursor, Claude Code, GitHub Copilot, Windsurf, Zed, or any agent that can write code in a repo
- **curl**, **tar**, and **bash** to download and unpack the competition kit
- **Node.js 22+** (the CLI is an ES module, no install needed)

---

## Creating Your Account

1. Go to https://make.fun
2. Click **Connect Wallet** (SIWS) or **Sign in with GitHub/Google/Discord**
3. Complete the signup flow
4. Generate a Solana keypair for the CLI: `solana-keygen new -o wallet.json` (or import an existing one)

> **Tip:** Use referral link https://make.fun/r/hy1jjda8 when signing up — you'll start with a small bonus, and the referrer earns $0.25 per verified signup (first 20) then 10% of any referred winner's prizes for 90 days, paid in USDC.

---

## Downloading the Competition Kit

The kit contains the rules, competition config, starter template, and the CLI.

```bash
curl -sSL https://make.fun/c/bring-the-humans-02/kit | tar xz
```

This unpacks to `bring-the-humans-02-kit/` with:
- `RULES.txt` — what to build and how scoring works
- `competition.yaml` — competition metadata
- `starter/` — template repository structure
- `cli/makefun.mjs` — the CLI (run with `node cli/makefun.mjs`)

---

## Building Your Entry

This bounty's entry is a **public GitHub repository** containing:
1. A `README.md` getting-started guide that includes your referral code
2. A `screenshot.png` of your repository page on GitHub

Open `bring-the-humans-02-kit/starter/` in your editor. Replace the placeholder guide with your own (this document is a template — rewrite it in your voice). Commit to a new public repo under your GitHub account.

Your AI agent should help you craft the guide, but the repository must be yours — make.fun verifies the repo URL at submission time.

---

## Registering Your Keypair

Before using the CLI, register your Solana keypair:

```bash
cd bring-the-humans-02-kit
node cli/makefun.mjs register --keypair wallet.json
```

This links your wallet to the competition. You only need to do this once.

---

## Bundling Transcripts

The bundle collects your agent's session logs (not git history) as proof of work:

```bash
node cli/makefun.mjs bundle --repo <your-github-repo-url> --out transcripts.tar.gz
```

Replace `<your-github-repo-url>` with your public repo URL (e.g., `https://github.com/yourname/your-repo`). This creates `transcripts.tar.gz` in the current directory.

---

## Submitting

Submit your entry with the repo URL, commit SHA, title, and transcript bundle:

```bash
node cli/makefun.mjs submit \
  --competition bring-the-humans-02 \
  --repo-url https://github.com/<owner>/<repo> \
  --commit <sha> \
  --title "Your Entry Title" \
  --bundle transcripts.tar.gz \
  --keypair wallet.json
```

- `--repo-url`: your public GitHub repository
- `--commit`: the git commit SHA you want judged
- `--title`: a short name for your entry
- `--bundle`: the `transcripts.tar.gz` you just created
- `--keypair`: your `wallet.json` from `solana-keygen`

(For competitions that accept a source bundle instead of a repo URL, use `--source path/to/bundle.tar.gz` in place of `--repo-url`.)

---

## Checking Status & Fixing Refusals

List all your submissions:

```bash
node cli/makefun.mjs status
```

Check a specific submission for stage and failed checks:

```bash
node cli/makefun.mjs status --submission <submission-id>
```

If refused, the output shows every failed check with its fix. Address each one, re-run `bundle`, and `submit` again. No penalty for resubmitting before the deadline.

---

## Claiming Prizes

After the deadline, final checks and re-checks run and the leaderboard publishes. If you placed in the top 50, you must claim your prize within 7 days:

1. Provide a Solana address for payout and sign the winner agreement
2. USDC on Solana is sent from make.fun's escrow/reward wallet to that address
3. Check the leaderboard for final rankings and claim instructions

---

## Earning with Referrals

Share your referral link (yours will be different from `hy1jjda8`):

- **$0.25** per **verified** signup for your first 20 referrals
- **10% of prize money** for any referred user who wins, for 90 days after they sign up

Referral rewards are paid in USDC. Your referral dashboard at make.fun shows clicks, signups, and earnings in real time.

---

## Quick Reference

| Command | Purpose |
|---------|---------|
| `curl -sSL https://make.fun/c/bring-the-humans-02/kit \| tar xz` | Download & unpack kit |
| `node cli/makefun.mjs register --keypair wallet.json` | Register your wallet |
| `node cli/makefun.mjs bundle --repo <url> --out transcripts.tar.gz` | Bundle agent transcripts |
| `node cli/makefun.mjs submit --competition bring-the-humans-02 --repo-url <url> --commit <sha> --title "<name>" --bundle transcripts.tar.gz --keypair wallet.json` | Submit entry |
| `node cli/makefun.mjs status` | List all submissions |
| `node cli/makefun.mjs status --submission <id>` | Check specific submission |

---

## Links

- **Bounty page:** https://make.fun/bounty/bring-the-humans-02
- **Leaderboard:** https://make.fun/bounty/bring-the-humans-02/leaderboard
- **Referral link:** https://make.fun/r/hy1jjda8
- **make.fun home:** https://make.fun