# Local validation — 30 October 2026

Validation used Node.js 24.21.0 and npm 11.19.0 on macOS.

## Completed

- Reconstructed and verified all 11 source checkpoints by exact retained paths, file bytes, and Git modes; new commits use the configured identity and current timestamps.
- Installed both lockfiles with `npm ci`. Node's default CA trust failed to validate npm's certificate chain. Using `NODE_EXTRA_CA_CERTS=/etc/ssl/cert.pem npm ci` succeeded for both packages with TLS verification enabled. No global npm settings or security checks were changed.
- All 188 automated tests passed (zero failures). These include isolated provider mocks, so this result alone is not live integration evidence.
- TypeScript and Vite production build passed.
- `judge:verify` passed; corrected and historical replay controls each passed 2/2 cases. Seeded and refusal controls correctly exposed different failures.
- The 20-case recorded challenge produced a report: candidate 18 passed, zero failed, two inconclusive. This replay made no new AI request.
- Presentation lint/typecheck, caption validation (8 narration clips, 73 pages, 4,755 frames), and bundle build passed.
- Source archive built and downloaded through the running API.
- Browser: landing page loaded, the comparison executed, the result displayed, and the test lab showed saved evidence.
- **Fresh AI:** invoked the real Codex connector through the browser using existing ChatGPT authentication. Both synthetic refund cases passed. The UI displayed the actual model decisions and saved run. Payments remained simulated; no PayPal call was made.
- Live HTTP checks covered state, operation status, README/license/archive responses, foreign-origin and invalid-host rejection, and JSON content-type enforcement.
- Live HTTP functional checks covered creating and approving a new scenario, exporting its agent request, evaluating it, exporting/replaying evidence, archiving the validation scenario, and reading persisted state. Missing approval/fault fields were rejected during request preparation, as expected; complete requests passed.

## Limits and outstanding findings

PayPal Sandbox credentials were not configured; actual order approval, capture, refunds, and provider readback were not exercised. Ollama was not installed/running, so its independent local model integration was not exercised. Fresh Codex inference was tested instead. The video bundle was built, but a full MP4 render was not performed. Browser validation was a focused desktop smoke test, not exhaustive cross-browser or mobile coverage.

`npm audit` reported two application dependency findings (body-parser: high; qs: moderate) and eleven presentation findings (ten high, one moderate, including Remotion dependency chains, zod and fast-uri). Lockfiles were retained exactly for source fidelity; no forced upgrades or audit suppression were applied. These findings require dependency remediation before broader deployment.

The production app is bound to `127.0.0.1:4318`. Runtime state, credentials, fresh AI evidence, logs and dependency directories remain ignored and are not published. The public repository contains reconstructed source, original bundled historical evidence, retained licenses/notices and newly written documentation.
