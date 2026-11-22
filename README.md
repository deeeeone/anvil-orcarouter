# anvil-orcarouter

An [Anvil](https://github.com/deeeeone/Anvil) provider plugin for [OrcaRouter](https://www.orcarouter.ai), giving Anvil access to OrcaRouter's free models through its OpenAI-compatible API.

## Requirements

- An OrcaRouter API key (keys issued by the [dashboard](https://www.orcarouter.ai) start with `sk-orca-`, per [OrcaRouter's docs](https://docs.orcarouter.ai/getting-started/get-api-key)).

## What it sends where

- Requests go to `https://api.orcarouter.ai/v1/chat/completions` and `/models` with your API key sent as `Authorization: Bearer <key>` (the bearer scheme documented by OrcaRouter). The key is entered in Anvil's settings.

## Install

In Anvil: **Settings → Provider → More providers → Add provider**, paste this repo's URL, confirm, and enter your API key.

Or locally: clone or download this folder, then **Add provider → From a folder**.

## Models

The file ships the current free list (confirmed live via `GET /models`); OrcaRouter's lineup rotates, so edit `anvil-provider.json` if a free model disappears. OrcaRouter also exposes the virtual `orcarouter/free` id that routes to whatever free model is available.

## Notes on the free tier

OrcaRouter applies lower rate and daily limits to free-tier usage and may reject oversized single prompts; expect occasional 4xx responses on the free package. Check the [OrcaRouter docs](https://docs.orcarouter.ai) for current limits.
