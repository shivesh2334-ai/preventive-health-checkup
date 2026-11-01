# Deployment and clinical scope

Repository: shivesh2334-ai/preventive-health-checkup
Intended Vercel project: preventive-health-checkup
Proposed team: shivesh's projects (team_ovdU2OR9i6opogdJ7os0n3BE)

Deployment awaits confirmation of that team: automatic approval review rejected project creation because the team had not been explicitly confirmed. No live deployment exists from this session.

Import this GitHub repository with framework Other, root directory repository root, no build command, no output-directory override. Vercel serves static files and api/review.js as a Node 22 function. Git integration should deploy main automatically after setup.

AI review needs AI_GATEWAY_MODEL set to a live vision-capable provider/model ID from https://ai-gateway.vercel.sh/v1/models. It uses VERCEL_OIDC_TOKEN automatically on Vercel or an encrypted AI_GATEWAY_API_KEY. Never put credentials into source code or the browser. No AI model request was performed during development. Missing configuration produces an explicit 503, not a simulated opinion.

AI accepts pasted report text and JPG/PNG written-report images. PDF files are listed locally; paste verified PDF report text for review. Reports are not durably stored. Client data remain in memory until reset/close. AI submission excludes the separate name and blood-group fields, but free-text and reports may contain identifiers: redact these before submission. Provider/Gateway retention and logging policies apply.

Limits: 4 files, each 2 MB, total 2.5 MB to stay below Vercel request limits after base64 encoding. Server also validates report sizes and consent. Same-origin browser policy and best-effort per-instance in-memory rate limits reduce misuse; these do not replace authentication or distributed rate limiting. Before offering paid/public AI review at scale, implement durable limits and patient/clinician authentication. No patient record database or medical-device validation is claimed.

Clinical logic offers the entire supplied catalogue but does not recommend every test to all adults. 20–39 and 40+ bands are organisational; screening uses additional age thresholds, anatomy and prior-test flags. Diabetes prompts are risk discussion, not a complete India-specific screening algorithm. Some selected risks are collected as context for clinician/AI review and do not automatically select a test. High-risk cancer family history requires individual specialist pathways. The app does not calculate a validated ASCVD risk score or prescribe drugs.

Verification: node --test (BMI, thresholds, no universal high-harm selections, urgent flags, consent and origin checks). node --check app.js and api/review.js. Browser workflow and live AI calls remain unverified until deployment. A clinician must verify OCR, units, ranges, pregnancy context, recommendations and referrals. A missing/normal screening result never rules out disease in a symptomatic person.
