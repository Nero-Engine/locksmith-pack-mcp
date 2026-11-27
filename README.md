# Locksmith Pack

Free tools a UK locksmith's AI assistant uses on the job: lockout and lock change quotes with call out and out of hours rates, BS 3621 and anti snap checks against what home insurers usually ask for, priced security upgrade plans, who a locksmith may let in and what to record, and car key quotes.

**Endpoint:** `https://locksmith-pack.nerolabs.workers.dev/mcp` (MCP, Streamable HTTP)
**Sign-in:** None. No account, no key and no sign-in: add the address and use it.
**How to connect:** https://locksmith-pack.nerolabs.workers.dev/docs
**Privacy:** https://locksmith-pack.nerolabs.workers.dev/privacy
**Support:** founder@neroengine.com

## Tools

| Tool | What it does |
|---|---|
| `list_capabilities` | What Locksmith Pack can do. Lists Locksmith Pack's tools, tasks and hours, parts and default costs, time of day factors, lock types, entry scenarios, car key types, default rates and what it deliberately does not do. |
| `quote_locksmith_job` | Locksmith job quote. Prices a locksmith job from a list of tasks: lockouts (non destructive or drill and replace), cylinder and mortice lock changes, nightlatches, uPVC gearboxes and multipoint locks, window and patio locks, letterbox guards, smart locks, key cutting and boardi... |
| `lock_standard_check` | Lock standard check against usual insurer wording. For each door (timber, uPVC, composite, aluminium, sliding patio, bifold, timber French), says whether its locks meet what UK home insurers usually ask for: a BS 3621 deadlock on timber final exit doors; an anti snap euro cylinder (TS 007 3 star, or 1 star ... |
| `security_upgrade_plan` | Priced home security upgrade plan. Checks every door with lock_standard_check, adds window locks and optional extras (letterbox guard, door limiter, door viewer, smart lock), and prices the whole upgrade in one visit: tasks merged, hours, parts, labour, minimum charge, margin and VAT, with t... |
| `access_and_entry_rules` | May I open this door? Entry and lock change rules. Before opening a door or changing locks for someone, returns a verdict (go, go_with_checks or stop), the checks to make, the record to keep, what to say, and the law, in plain words. |
| `car_key_quote` | Car key quote for auto locksmiths. Prices a car key: key type (basic_metal, transponder, remote, flip_remote, proximity_smart), spare or all keys lost, premium make (x1.4), quantity, mobile call out, blank cost plus markup and programming time, with a range and the checks: V5C and ID before ... |
| `trade_profile` | Check the locksmith's business details. Checks the locksmith's own details (Nero Trade Profile v1: trading name, Companies House number, trade body or scheme and number such as the Master Locksmiths Association, postcode, contact, Nero Work services) and returns them cleaned, with a stable `nero_... |

Every tool carries a plain title and the read-only, destructive and open-world hints, so your AI app can ask before anything that changes data.

## Skills

The server also serves ready playbooks over the MCP Skills extension (`skills/list`, `resources/read`), so an AI app that supports skills can follow them:

- **quote-a-locksmith-job**: Turn a customer call or message into a safe, priced locksmith job for a UK locksmith: check the locksmith may open the door or change the locks, pick the tasks, price them with call out and out of hours rates, and write the price the customer agrees before work starts. Use when a locksmith says "quote this", pastes a lockout or lock change enquiry, or lists jobs.
- **secure-a-home**: Check a UK home's door and window locks against what home insurers usually ask for and price the upgrade in one visit: BS 3621 on timber doors, anti snap cylinders on uPVC and composite doors, anti lift on patio doors, window locks, and keyless exit rules in flats and HMOs. Use when a locksmith or customer asks "do my locks meet my insurance", "what should I fit", after a burglary, or for a new home lock change.

## Connect

- **Claude (web or desktop):** Settings, Connectors, Add custom connector, paste the endpoint.
- **ChatGPT:** Settings, Apps and connectors, Advanced settings, switch on Developer mode, then Create, paste the endpoint, No authentication.
- **Claude Code:** `claude mcp add --transport http locksmith-pack https://locksmith-pack.nerolabs.workers.dev/mcp`
- **Gemini CLI:** `gemini extensions install https://github.com/Nero-Engine/locksmith-pack-mcp`
- **Cursor, VS Code, Windsurf and others:**

```json
{ "mcpServers": { "locksmith-pack": { "type": "http", "url": "https://locksmith-pack.nerolabs.workers.dev/mcp" } } }
```

## Try asking

- "Price a night time lockout on a uPVC front door, in case I have to drill the lock."
- "My customer's back door is timber with a 2 lever mortice and the front is a composite door with an unmarked cylinder. Does that meet their insurance, and what should I fit?"
- "A landlord wants me to change the locks while the tenant is still living there. Can I?"

## Good to know

- Built for UK locksmiths. Every answer shows its working and sources and lists what the trade must check. The trade doing the work stays responsible for it.
- Free forever: no sign-up, no key, no daily cap, no paid plan.
- Labour hours are indicative for a typical medium car, not a maker's labour time, and prices use your own parts costs. Every default rate is labelled in the answer; pass your own.
- Lock standards (BS 3621, BS 8621, BS 10621, TS 007, Sold Secure SS312, PAS 24) are checked against what UK home insurers usually ask for; the customer's own policy wording wins. Entry law (Protection from Eviction Act 1977, Taking Control of Goods Regulations 2013, PACE section 17 and others) is summarised in our own words with the source named in every answer. Not legal advice.
- Postcodes are placed in their council area with postcodes.io (Office for National Statistics, Open Government Licence).

## Privacy

What is kept, what is never kept, and how to get data deleted: https://locksmith-pack.nerolabs.workers.dev/privacy. Usage counts log the tool name, time, AI app name, country and a one-way scrambled caller code; never your questions, the answers or IP addresses.

This repository holds the listing only (README and server.json). The server runs at the endpoint above.

Built by Nero Labs (Nero Engine Group Ltd, UK).
