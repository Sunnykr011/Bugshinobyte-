

---

🧠 S-Tier Recon Strategy: From Wappalyzer to Critical Findings

🧩 Format: Phase-wise | Practical | Smart Notes | Mental Models + Pro Tips


---

✅ Phase 1: Recon Ground Zero – Start Here Always

> Goal: Set base context before using any tool or scanning. Become aware of what you're hunting.



📌 What to do:

1. Open the target in browser

Manually observe title, favicon, UI structure.

Check if login/signup exists, or it's marketing-only.

Note subdomains or sections (blog., app., api.)



2. Run Wappalyzer or BuiltWith

Identify tech stack: e.g., WordPress, Next.js, React, PHP, Nginx, AWS, Firebase, etc.



3. Start a "Recon Profile" note for this target:

Tech stack

Subdomain style

Industry: SaaS? Ecommerce? Banking?

CDN or cloud? (Check response headers, DNS)




> 🧠 Mental Model: “Tech stack tells me the attack map.”
If you know what tech is being used, you already know what types of bugs are possible and what is unlikely.




---

✅ Phase 2: Stack-Aware Recon – Use the Tech Stack Logically

> Goal: Intelligent scanning based on what you found.



📌 What to do:

1. From Wappalyzer output, create a recon checklist.
Examples:

If React/Angular → look for client-side XSS, JS-heavy endpoints.

If WordPress → focus on plugins, admin panels, XML-RPC.

If Laravel (via headers) → look for .env, debug mode, artisan endpoints.

If AWS → check for S3 misconfig, Cognito exposure, EC2 metadata.



2. Use tech-specific dorks on GitHub/Shodan/Google

filename:.env "target.com"

site:target.com inurl:wp-content

favicon.hash:XXXX on Shodan

npm audit if you find package-lock.json on GitHub




> 🧠 Pro Tip: Tech + dork = sniper scan.
Instead of scanning everything blindly, you now search only where high-probability bugs exist.




---

✅ Phase 3: High-IQ Asset Discovery

> Goal: Discover real attack surface, not just root domain.



📌 What to do:

1. Subdomain Enumeration

Use crt.sh, dnsdumpster, assetfinder, subfinder, etc.

Prioritize: api.*, dev.*, admin.*, test.*



2. JS File Extraction

Run gau, waybackurls, hakrawler, etc.

Extract JS and parse with LinkFinder or SecretFinder.



3. Virtual Host Bruteforcing (if wildcard DNS)

Use ffuf or vhoster to discover hidden apps.




> 🧠 Mental Trigger: “Every subdomain is a new recon universe.”
Never assume main domain is the only thing worth checking. Often, the bug lives in old.blog.beta.target.dev.




---

✅ Phase 4: Behavioral Recon & Subtle Signals

> Goal: Catch what scanners ignore.



📌 What to do:

1. Custom 404 behavior?

Observe how the app handles wrong URLs.
→ Can indicate open redirects or path-based auth logic.



2. Check Title Mismatches

Use httpx or eyewitness to find inconsistencies.
→ Admin panels may have different titles.



3. Analyze Response Codes

Look for 403, 401, or even 500 on weird endpoints.



4. robots.txt / sitemap.xml

Often ignored but can lead to /admin, /private, /test/, etc.




> 🧠 Pro Tip: Bugs love hiding behind behavior, not just URLs.
Look at how the app reacts to odd inputs — that’s where magic is.




---

✅ Phase 5: Filter, Note, Focus

> Goal: Don’t get overwhelmed. Focus on what matters.



📌 What to do:

1. Filter all results (gau, waybackurls, subdomains, JS endpoints)

Sort by:

Repetition frequency

JS mentions

Non-standard paths




2. Use tags in Obsidian or Markdown like:

## 🔍 API Endpoint
- URL: https://api.target.com/v1/devtest
- Found via: gau + wayback
- Looks internal or staging


3. Build "Target-Specific Recon Tree"

Tech stack → leads to → plugin paths

JS files → leads to → endpoints

Subdomain style → leads to → naming pattern guesses




> 🧠 Mental Model: “Less noise, more signals.”
Your job isn’t to scan 10k URLs — it’s to find 10 that are unusual.




---

✅ Current Phase Complete?

If you’ve done till here on one target, you’ve built a high-IQ recon map.

💡 Tell me “Phase Complete” and I’ll give you the next layer:

Payloadless recon

Behavioral fingerprinting

Cloud logic fuzzing

S3/Cloudfront misconfig checks

CI/CD & startup dev flow-based recon



---

⚔️ BONUS: S-Tier Recon Mental Tactics

Situation	Think Like This

Too many URLs?	“Where’s the odd one out?”
Found old tech in Wappalyzer?	“Outdated = vulnerable.”
Found JS file?	“Parse it. It hides future bugs.”
Site has 403 pages?	“They don’t want me here. Let me in.”



---

🚀 Conclusion

Your recon should feel like this:

> You know why you're scanning something, not just running tools randomly.



You:

Start with tech awareness (Wappalyzer)

Build a logical map

Perform high-signal checks

Keep notes and patterns for reuse

Don’t rely on brute-force — use logic + behavior