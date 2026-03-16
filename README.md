# google-captcha-v3-tester

A simple local static tester for Google reCAPTCHA v3.

✅ Live demo: https://thyashley.github.io/google-captcha-v3-tester/

## What is this about?

This project is a single-page static app (`index.html`) that lets you:

1. Generate a reCAPTCHA v3 token from a frontend site key (using the Google reCAPTCHA script).
2. Copy the generated token.
3. Paste your secret key and token to verify against Google’s `/siteverify` API.

It is designed for manual testing and debugging your reCAPTCHA keys and server verification flow.

## Run locally (macOS / Linux)

1. Open a terminal in this project folder.
2. Install Node.js/npm if needed (optional; this uses Python's built-in server).
3. Run:

```bash
npm start
```

4. Open your browser to:

```text
http://localhost:8080
```

(Optional) quickly open from terminal:

```bash
npm run open
```

## Alternative local run (pure Python without npm)

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## Usage

1. Enter your reCAPTCHA site key in Step 1 and click "Generate New Token".
2. Copy the token from Step 1.
3. Paste your secret key and token into Step 2 and click "Verify with Google API".
4. Read the API response in the verification panel.

### Troubleshooting token generation

- Ensure you are using a valid reCAPTCHA v3 site key (starts with `6L...`).
- Make sure your key is enabled for the current domain (localhost in this tester).
- If you see browser console errors, re-run and check the console for script loading errors.
- Ensure your reCAPTCHA v3 site key is a valid v3 key and is authorized for `localhost` (or your local host domain). If domain mismatch occurs, token generation fails.
- If the token is still empty, `grecaptcha.execute` may be blocked by missing site key, invalid key, or domain restrictions.
