# anvil-orcarouter

An [Anvil](https://github.com/deeeeone/Anvil) provider plugin for [OrcaRouter](https://www.orcarouter.ai), giving Anvil access to OrcaRouter's free models through its OpenAI-compatible API.

## Requirements

- An OrcaRouter API key (starts with `sk-orca-`).

## What it sends where

- Requests go to `https://api.orcarouter.ai/v1/chat/completions` and `/models` with your API key sent as `Authorization: Bearer <key>`. Nothing else is contacted; the key stays in the macOS Keychain.

## Install

In Anvil: **Settings → Provider → More providers → Add provider**, paste this repo's URL, confirm, and enter your API key.

Or locally: clone or download this folder, then **Add provider → From a folder**.

## Models

The lineup of `-free` models changes often; the file ships the current free list. Anvil also lists the live catalog from `/models`, including the virtual `orcarouter/free` id that routes to whichever free model is available.

## Notes on the free tier

Unpaid accounts are limited to roughly 10 requests/min and 50 requests/day; a large single prompt may be rejected with a prompt-cap error rather than a normal rate-limit error. Expect occasional 4xx responses on the free package.
