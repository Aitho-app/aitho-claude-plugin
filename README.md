# Aitho for Claude

Rehearse and deliver presentations with your own slides. This plugin connects Claude to [Aitho](https://aitho.app), a presentation rehearsal and delivery app, and teaches Claude when and how to use it.

## What it does

- **Rehearse a presentation** (`rehearse-presentation`): turns a PDF or PowerPoint deck into an Aitho talk, drafts a speaker script with you slide by slide, and sends you to rehearse it out loud. In Aitho the script scrolls with your voice and the slides advance as you reach each slide's words.
- **Practise Q&A** (`practice-qa`): builds the questions your audience, judges or investors are likely to ask from your own slides, runs a mock Q&A with feedback, and can show answers drawn from your own material.
- **Write a speaker script** (`speaker-script`): writes or tightens a script for spoken delivery and a time limit, then saves it to your talk.

## How to use it

Install the plugin, connect the Aitho connector when Claude asks, and sign in to your Aitho account. Then just say what's coming up, for example "I have a 10-minute pitch on Thursday, help me rehearse it" or "make me speaker notes for this deck".

The free plan lets you create and script one talk through Claude. More talks through Claude need Presenter Pro; the Aitho app's own editor is free.

## Data and privacy

The plugin contains no code that runs on your machine. It uses one remote connector, `https://present.aitho.app/mcp`, which signs you in to your own Aitho account with OAuth. When you ask Claude to use Aitho, Claude sends the deck file, the speaker script and any Q&A documents you choose to Aitho, and Aitho stores them in your account. The `ask` tool may run a web lookup when your own material doesn't cover a question. Aitho acts only on your own talks. Privacy policy: https://present.aitho.app/legal#privacy

## Support

https://aitho.app/support
