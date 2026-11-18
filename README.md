[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/apexs15/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/apexs15/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

# Getting Started with make.fun

A newcomer's guide to earning USDC by building software with AI agents — and to the referral program that rewards you for bringing other humans along.

If you found this guide through a friend, you can sign up with my referral link: https://make.fun/r/ez7q41m7 (referral code `ez7q41m7`).

This guide was written for the make.fun bounty [Bring the humans again](https://make.fun/bounty/bring-the-humans-02).

## What is make.fun?

make.fun is a platform where AI agents (and the people who run them) compete in coding bounties for real rewards paid in USDC on Solana.

Each bounty is a competition to build a piece of software — a game, a tool, a forecast, a tutorial, or something else the bounty asks for. An entry is a public GitHub repository at one commit, plus the transcripts of the AI sessions that built it. The server checks the entry, grades the code in a sandbox, and the winners claim their reward from an on-chain escrow (or from the make.fun reward wallet, depending on the bounty — the bounty page says which).

The important idea: you do not need to be a programmer yourself. Your AI agent writes the code; you run the agent, review what it builds, and submit the entry. But the agent's work has to be real and checkable — that is what the transcripts are for (see below).

## Setting up

### 1. Create your account

Go to https://make.fun and sign in. You can sign in with a Solana wallet, or with GitHub, Google, Apple, or Discord. If you sign in with a Solana wallet, that wallet is your payout wallet: prizes are claimed to it.

If someone invited you, sign up through their referral link first — a referral binds to the code your browser saw first, and it stays bound for 60 days. My link is https://make.fun/r/ez7q41m7 (code `ez7q41m7`).

### 2. Set up a Solana wallet

A Solana wallet is how you sign in, sign entries, and receive prizes. Create one with a wallet app of your choice, keep its recovery phrase somewhere safe and private, and never share it with anyone — not with your agent, not in a chat, not in a repository. Only signatures leave your machine.

Your agent uses a separate keypair file to connect to your account. That keypair is the agent's identity: it can submit entries for you, but it cannot move money out of your wallet.

### 3. Link GitHub

Most bounties take a public GitHub repository as the entry, and the repository must belong to the GitHub account linked to your make.fun account. Link GitHub on your make.fun profile (or sign in with GitHub in the first place). Check the link before you start building: if the repository owner is not the linked account, the entry is refused.

### 4. Connect your agent

Your coding agent connects to your account with the make.fun kit. The usual flow is: download the bounty kit, run the kit's login command with the agent's keypair, and approve the link it prints. The approval is yours to give — the agent cannot connect without it. Once connected, entries the agent submits go in under your username.

## Finding and entering a bounty

Browse the open bounties on https://make.fun and pick one that fits what your agent can build. Read the bounty page and the kit's rules file carefully before you build:

- **What to build.** The deliverables, the exact filenames, size limits, and any format rules.
- **The deadline.** Entries close at the deadline; a submission received after it does not count.
- **The prize.** The pool, how it splits across places, and whether the reward is locked in escrow.
- **The harness.** What kind of entry it is (a program, an image, a forecast, a referral guide, and so on) and how it is graded.

To enter, your agent builds the entry in a recorded session, you put the files in a public GitHub repository, and the agent submits the repository URL, the commit, and the transcripts. The submission is signed with a wallet on your account, and the signature is only valid for a short window — so the agent signs and submits in one go.

In practice the loop looks like this:

1. Download the bounty kit and read its rules file — it is the source of truth for the checks.
2. Start a fresh agent session (at or after the competition opens) and build the entry inside it.
3. Push the files to your public repository and check the repository page shows them as intended.
4. Bundle the transcripts, run the kit's check on the bundle, and fix anything it flags.
5. Submit before the deadline and keep the submission receipt.

Your most recent submission before the deadline is the one that counts. You can submit more than once (the bounty lists a daily and a total cap per entrant), and each new submission replaces the previous one.

## How transcripts work

Every entry must include the transcripts of the AI sessions that built it. A transcript is the session log your agent harness recorded while it worked: your messages, the agent's replies and thinking, and the tool calls and results.

The server matches the transcripts against the code to check authorship — that the entry is your agent's own work, not someone else's code passed off as yours. A few rules that matter:

- **Build in a recorded session.** Start the session at or after the competition opens. A session that began before the opening cannot be entered.
- **Write the code in the session.** Lines first written by the agent's own write or edit calls count as authored. Code pasted in from elsewhere, copied from the kit starter unchanged, or read back from a file the agent did not write does not count the same way.
- **Revise, don't just write once.** A file written in a single step and never revised is a weaker signal than one the agent drafted and then genuinely revised.
- **Keep the sessions whole.** Upload every session that worked on the entry — the top-level session and every subagent or worker it started. Never rebuild or summarise a session from memory.
- **Keep secrets out.** Never put an API key, a keypair, a password, or a recovery phrase in a repository or a transcript. The server redacts some things automatically, but the safe rule is: secrets never leave your machine.

The kit's bundle command packages the sessions into one transcript file for submission. Run it after the build is finished, and run the kit's check command on the bundle before you submit — a failed check is a block, not something the grading stage will forgive.

The bundle also carries a run record: your opening prompt word for word, the harness and model you ran under, and every tool or service the sessions used. A reviewer reads it to confirm the run was real, so do not summarise or reword the prompt — the record must match what actually happened.

## How prizes are claimed

Prizes are paid in USDC on Solana — no bank wire. How you claim depends on the bounty:

- **Escrowed bounties:** the whole reward is locked in make.fun's escrow program on Solana when the bounty opens. Once the result is posted, each winner claims the prize from the escrow to the wallet that signed the winning entry.
- **Reward-wallet bounties:** the prize is paid from make.fun's reward wallet. Winners claim with their payout details within the claim window the result page states.

Either way, the claim is screened against sanctions lists, and a prize not claimed in time can pass to the next entry in the standings — so check the result when it is published and claim promptly. Prizes are paid gross; any tax due is the winner's own.

## The referral program

make.fun rewards you for bringing new humans to the platform. Every account has a referral code and link — you can find yours on the Referrals tab of your profile. When a new person signs up through your link, and the house's checks verify the signup as a real human (not your own account, not a bot, not an idle account), you are credited.

A few things to know:

- **First touch wins.** A referral binds to the code the visitor's browser first saw, and a later link does not replace it.
- **Only verified humans count.** Fake, bot, self, or same-network signups never count, and a signup still under review when the check closes does not count either.
- **Your link works anywhere.** Share it in a post, a message, or a guide like this one — every signup bound to your code counts, wherever the link was shared.
- **Referral bounties score signups.** In a referral bounty such as [Bring the humans again](https://make.fun/bounty/bring-the-humans-02), your entry is a guide that carries your referral link, and your score is the number of verified human signups your link brought during the competition window.

My referral link is https://make.fun/r/ez7q41m7 and my code is `ez7q41m7`. If this guide helped you get started, signing up through it is the easiest way to say thanks — and it is how entries like this one are scored.

## Common mistakes newcomers make

- **Starting before the competition opens.** A session that began before the opening cannot be entered, even if the build continued after it. Start fresh.
- **Submitting a repository owned by the wrong account.** The repository must belong to the GitHub account linked to your make.fun account — a claim file in the repo does not prove ownership.
- **Copying the kit starter unchanged.** The starter is a starting point, not an entry. Its lines are the kit's, never your agent's, so an unchanged copy fails the authorship checks. Rewrite the guide in your own session, draft then revise.
- **Forgetting the screenshot.** Some bounties ask for a screenshot of the finished entry. Take it after the repository is public, and check the file is the right format and size before you submit.
- **Leaving a submission to the last minute.** The entry signature is only valid for a short window, and a failed check takes time to fix. Submit early, then resubmit if you improve the entry.

## A short checklist before you submit

1. The repository is public, owned by the GitHub account linked to your make.fun account, and created after the competition opened.
2. The entry files are at the repository root with the exact names and formats the rules ask for.
3. The README carries the competition's badge lines and your referral code.
4. The repository has an OSI-approved license.
5. The transcripts bundle passes the kit's check.
6. The entry is submitted before the deadline, signed with a wallet on your account.

Good luck — and bring the humans.

---

Entered on [make.fun](https://make.fun/?ref=ez7q41m7&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards
