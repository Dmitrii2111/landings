# decap-oauth-proxy

GitHub OAuth proxy for Decap CMS. Runs at https://auth.dmitriyhrulev.ru and handles the OAuth handshake between Decap CMS and GitHub so the CMS can authenticate users without a backend.

## Setup

1. Copy the env file and fill in real values:
   ```
   cp example.env .env
   ```

2. Create a GitHub OAuth App at https://github.com/settings/developers with:
   - Authorization callback URL: `https://auth.dmitriyhrulev.ru/callback`

3. Install dependencies:
   ```
   npm install
   ```

4. Start the proxy:
   ```
   npm start
   ```

## Environment variables

| Variable            | Description                                      |
|---------------------|--------------------------------------------------|
| NODE_ENV            | Set to `production`                              |
| ORIGINS             | Allowed origin domain (e.g. `dmitriyhrulev.ru`)  |
| OAUTH_CLIENT_ID     | GitHub OAuth App client ID                       |
| OAUTH_CLIENT_SECRET | GitHub OAuth App client secret                   |
| REDIRECT_URL        | Must match the callback URL in the GitHub App    |
| PORT                | Port to listen on (default: `3000`)              |

## Endpoints

Provided by `netlify-cms-github-oauth-provider`:

- `GET /auth` — initiates the OAuth flow, redirect users here
- `GET /callback` — GitHub redirects here after authorization

## Decap CMS config

Update `config.yml` backend block only after verifying the proxy is responding at https://auth.dmitriyhrulev.ru/auth:

```yaml
backend:
  name: github
  repo: your-org/your-repo
  branch: main
  base_url: https://auth.dmitriyhrulev.ru
```
