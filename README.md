Kippers Bot

A lightweight, Linux-only Lichess BOT client designed for the Kippers chess engine.

Downloads

Download "Kippers-Bot-0.1.2-Linux-x86_64.zip" from the "Releases page" (https://github.com/rrttyynn/Kippers-Bot/releases).

The release package includes the Linux x86-64 executable, source code, configuration example, and deployment instructions. The Kippers chess engine must be provided separately.

Features

- Outgoing challenges only: all incoming challenges are declined.
- One game slot, including a pending outgoing challenge.
- Additional outgoing challenges are cancelled while busy.
- UCI engine support with Ponder.
- Automatic reconnection and game recovery.
- Hidden API token entry and token storage with owner-only permissions.
- Single-threaded engine configuration by default.

If an additional game starts before its challenge can be cancelled, the client attempts to abort it. If aborting fails, it continues the original game and reports the extra game for manual handling.

Requirements

- Linux x86-64.
- A dedicated Lichess BOT account.
- A Lichess API token with the "bot:play" permission.
- A Linux UCI chess engine, such as Kippers.

Create your token at:
https://lichess.org/account/oauth/token

Quick Start

Extract the release ZIP and open a terminal in the extracted directory.

Place your Linux Kippers executable in that directory as "kippers", then run:

chmod +x bin/kippers-bot kippers
./bin/kippers-bot init --engine "$PWD/kippers"
./bin/kippers-bot token set
./bin/kippers-bot check
./bin/kippers-bot run

Enter your API token when prompted. Keep it private.

Playing Games

1. Start Kippers Bot and leave it running.
2. Sign in to the same BOT account in your browser.
3. Challenge another BOT from the website.
4. Once the challenge is accepted, Kippers plays automatically.

Select a rated challenge if you want a rated game, subject to Lichess rules and the opponent accepting it.

Incoming challenges are always declined, even while idle. Automatic acceptance cannot be enabled.

Ponder

Ponder allows the engine to search during the opponent's turn. A matching prediction continues with "ponderhit"; a different move stops the prediction and starts a search from the actual position.

Ponder uses CPU time during the opponent's turn.

Upgrading

Finish any active game and stop the old client before upgrading. Replace "bin/kippers-bot", then restart it. Existing token and engine configuration can continue to be used.

For version 0.1.2, start the client before sending a new challenge from the website.

Validation

Version 0.1.2 passed 43 development checks, including UCI and Ponder checks with Kippers. Live play with a real Lichess BOT account has not yet been verified.

See the README included in the release package for additional deployment instructions.
