# good_homes_prompt_api_google

Standalone external prompt API (Google-focused) for Good Homes Visualizer.

## Purpose
- Keeps Google-oriented prompt logic separate from the main app.
- Uses the same `/build-prompt` contract as `good_homes_prompt_api`.
- Lets the main server switch by changing `PROMPT_API_URL` and `PROMPT_API_KEY`.

## Endpoints
- `GET /health`
- `POST /build-prompt` (requires `Authorization: Bearer <PROMPT_API_KEY>`)

## Quick start
1. Copy `.env.example` to `.env` and fill values.
2. Install dependencies: `npm install`
3. Run dev server: `npm run dev`
4. Default port: `8789`

## Main app integration
In main app `.env.server`:
- `PROMPT_API_URL=http://localhost:8789/build-prompt`
- `PROMPT_API_KEY=<same key as this repo>`

No code changes are required in the main app if the contract is unchanged.
