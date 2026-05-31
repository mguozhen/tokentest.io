# cctest Research Notes

Date: 2026-05-28

## What Was Observable

- The apparent public cctest app host was returning HTTP 502 during research.
- Clauddy's advanced docs describe a Claude Code detection tool at `cctest.blueshirtmap.com`.
- The documented flow is a single-page test experience:
  - Open test page.
  - Enter Claude Code compatible API URL.
  - Enter API key.
  - Select or enter a model.
  - Run a built-in prompt and inspect whether the response matches Claude Code behavior.
  - Optional signature length check by converting the prompt to a curl request and copying a signature value.

## Product Shape

cctest is positioned as a focused compatibility probe:

- Narrow target: Claude Code compatibility.
- Fast feedback: success/fail, response content, curl-friendly prompt.
- Practical audience: operators of Claude Code routers and buyers checking whether a provider is genuine.

## Gaps To Exploit For TokenTest

TokenTest should not be only a "does it answer like Claude" checker. The stronger wedge is model/router truth:

- Model availability and alias reconciliation.
- Actual model returned vs requested model.
- Usage integrity: input/output/cache tokens must be present and plausible.
- Nonce replay guard: every run must echo a unique nonce.
- Read timeout and long output stability.
- Claude Code behavior claims: `/compact`, local tool write, permission bypass truthfulness.
- Billing status: explicitly separate request-side evidence from real backend billing.

## Recommended Tokentest.io Positioning

TokenTest is a verification console for AI middle-layer buyers:

- "Prove the model, route, usage, and billing before procurement."
- Primary artifact: shareable HTML evidence report.
- Core CTA: run a verification matrix, not just one prompt.

## Sources

- Clauddy docs: `https://docs.clauddy.com/en/advanced/cc-test.html`
- cctest host observed via docs: `https://cctest.blueshirtmap.com`
