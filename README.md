# ai chatbot integration with gohighlevel: What CloseBot Costs, How to Wire It Into a Sub-Account, and When It Beats the Bot You Already Have

Most people typing this query into Google are not looking for a definition of "chatbot." They already pay for GoHighLevel. Their real question is narrower: which AI chatbot should I connect, how does the connection actually get made, what does it cost per month, and is the platform's own Conversation AI good enough that I can skip the third-party tool entirely?

There is no single answer, because there are two completely different routes into the same CRM. One is native, billed per location, and improving with every release. The other is a third-party agent layer that sits on top of the CRM and takes over the text conversations already flowing through it. CloseBot is the best-known example of the second route, and it is the one most agencies end up evaluating.

Here's how both work, what each costs right now, and how to decide without burning a month on the wrong setup.

## The two routes into GoHighLevel

**Route one: the platform's own AI.** GoHighLevel ships Conversation AI, which operates as an agent inside the CRM. You create an agent, assign channels, define goals, and launch it. Billing runs per location: pay-per-use at token cost, or one of two subscription tiers that bundle usage.

**Route two: an external agent platform.** CloseBot connects through a native integration with HighLevel (and LeadConnector, HubSpot, custom CRMs, or a plain webhook), then listens for messages on the channels your CRM already handles. It replaces the human who would normally sit in the Conversations inbox qualifying leads and booking appointments.

The practical difference is where the intelligence lives. With Conversation AI, the reasoning and the prompts live inside GoHighLevel along with everything else. With the second route, you are buying a dedicated product built only for lead qualification and booking, and pointing it at your existing CRM. That is either a strength or an unnecessary extra invoice, depending on how much of your revenue runs through AI-set appointments.

## What GoHighLevel's own AI costs in 2026

If you want to judge the native option fairly, start with current pricing from HighLevel's own help centre, since third-party blogs still quote older numbers:

| Plan | Price | Conversation AI allowance |
| --- | --- | --- |
| Pay-per-use | No monthly AI fee | Billed at token cost |
| AI Employee Growth | $50/month per location | 1,000 agent responses/month, overages at pay-per-use rates |
| AI Employee Unlimited | $97/month per location | Unlimited, subject to fair use |

Two details matter more than the headline price. Agent Studio is not included in any subscription tier and stays pay-per-use across all three plans. And rebilling AI Employee usage to your clients requires the $497/month agency plan, which changes the economics fast if you resell AI to sub-accounts.

At four or more sub-accounts, the Unlimited tier is $388/month before you have added anything else. That number, not the per-message rate, is what pushes most agencies toward evaluating a third-party agent platform.

## How the CloseBot + GoHighLevel connection actually works

CloseBot does not connect to Instagram, WhatsApp, or SMS itself. Its own documentation is explicit about this: it piggybacks on whatever channels your CRM supports. Your CRM is the nervous system, CloseBot is the brain.

In practice that means:

- A lead messages your business on SMS, web chat, email, or a social DM that is already wired into your GoHighLevel Conversations inbox.
- CloseBot picks that message up from the connected sub-account and decides how to respond based on the agent you built.
- Qualification answers get written back into the contact record, tags get added or removed, and the agent can book straight onto a GoHighLevel calendar.
- When a conversation needs a human, a tag flips and the AI goes quiet while your team takes over.

Nothing leaves your CRM's channels. You are not moving conversations into a separate inbox and syncing them back.

## Connecting a sub-account, step by step

The OAuth connection itself takes a couple of minutes. The agent build is where your time goes.

1. **Create the CloseBot account.** The free plan needs no credit card and includes one agent, one user seat, 100 messages a month, 1 MB of knowledge storage, and unlimited CRM connections.
2. **Add a source.** Open Sources, click New Source, choose HighLevel Sub-Account, and hit Connect.
3. **Authorise the app.** A HighLevel OAuth window opens. Pick the workspace and the specific sub-account you want connected, then approve the permissions.
4. **Tick the field permission.** Back inside CloseBot, enable "Allow CloseBot to create/update fields" so the agent can write qualification data into custom contact properties.
5. **Confirm the source.** Click Add Source and you land on a list showing the live connection.
6. **Build or load a job flow.** Start from scratch, pick one of the templates, generate one from an AI prompt, or adapt a pre-built flow. A basic qualified flow collects name and email in one objective node, answers questions in a conversation node, then jumps to a booking sub-flow when the lead asks for a demo.
7. **Connect the calendar and a persona.** The GHL Booking node lets you select a calendar from a dropdown or paste a calendar ID. You cannot publish a flow without attaching a persona, which controls tone, timing, and how messages get split.
8. **Set your filters.** Channel filters and tag filters decide exactly when the agent is ON or OFF. A typical setup allows SMS only, requires a specific lead tag, and blocks a tag like `ai off` so a human can silence the bot per contact.
9. **Test, then publish.** The testing portal runs conversations before anything goes live, and you can roll back a flow or pause the AI on a single conversation at any point.

One thing worth internalising early: the agent does not run on a fixed script. It works through objectives and reasons its way through the conversation, which is why the knowledge library matters. Upload your offers, pricing rules, service details, and objection answers, and keep them current. A stale knowledge base is the single most common cause of an agent saying something you would not.

> Worth knowing: CloseBot does not offer "bring your own key." You cannot plug in your own OpenAI or Anthropic key to cut model costs. On paid plans you choose the provider per persona from OpenAI, Anthropic, Gemini, or Grok, and the system falls back automatically if your primary model fails.

## Building an agent that books rather than chats

The difference between a demo that impresses and an agent that fills a calendar comes down to a handful of design choices.

**Split your messages.** Real setters do not send a paragraph. Persona settings let you add typing delays and break responses into separate messages, which is the single biggest lever on reply rates.

**Use tags as switches, not decorations.** A `ready-to-book` tag triggers the scheduling link, `dnd` stops responses, `lead-qualified` hands off to sales. That keeps GoHighLevel workflows and the agent speaking the same language instead of fighting each other.

**Give it tools.** Agents can call Stripe for payment collection, pull property data, or hit a custom connector when your stack needs something specific. For real estate and home services, that is the difference between answering questions and actually qualifying.

**Let Smart FAQ flag the gaps.** When the agent is not confident, it notifies you instead of inventing an answer. You answer once, and CloseBot can follow up with every lead who asked that question.

If you want to see how the flow builder, booking node, and filters fit together before committing, 👉 [set up a free CloseBot account and build your first agent](https://app.closebot.com/register?fpr=li87).

## CloseBot's current plans and prices

The plans page splits into a business track and an agency track. The business track includes message costs in the base price; the agency track meters messages and lets you rebill them.

| Plan | What you get | Price | Billing | Get started |
| --- | --- | --- | --- | --- |
| Free | 1 agent, 1 user seat, 1 MB knowledge storage, 100 messages/month, unlimited CRM connections | $0 | Always free | [Start on the free plan](https://app.closebot.com/register?fpr=li87) |
| Core (Business) | Message costs included in the base price, 500 messages/month included, 15+ templates (50+ extra on annual), human support, extra seats at $5 each, add-on storage and agents | $64/month; $53/month equivalent billed annually as $640/year | Monthly or annual | [See the Core business plan](https://app.closebot.com/settings?tab=subscription&plan=business&toggle=monthly&fpr=li87) |
| Core (Agency) | Unlimited agents across unlimited sources, flat $0.012 per message with rebilling, white-label client portal, rebill all costs, extra seats at $5 each | $397/month (annual billing lowers the monthly equivalent) | Monthly or annual | [See the agency plan](https://app.closebot.com/settings?tab=subscription&plan=agency&toggle=monthly&fpr=li87) |
| Growth | HIPAA compliance, quarterly audits, 99.99% priority uptime, priority support, SLAs, 50+ templates, high volume | Custom quote | Quoted | [Request the Growth plan](https://app.closebot.com/a?fpr=li87) |

Alongside the base subscription, usage charges apply on the agency track, and the business track pays an overage rate once you pass your included ceiling. A message equals one segment, unless you enable the Agent Node's unlimited mode, where billing switches to token costs and a single message can consume several segments. Storage and seats are rebillable on agency accounts.

Business volume scales through a slider that runs from 100 up to 100K+ monthly messages, with the included ceiling rising as you pay more. A third-party pricing review published in August 2026 lists roughly $84/month for 1,000 included messages and $176/month for 5,000, which is a useful sanity check before you commit to a tier.

## What the integration costs at the scale most agencies actually run

Say you are an agency with ten sub-accounts and roughly 5,000 AI messages a month across all of them.

On the agency plan you pay $397 base plus 5,000 × $0.012 in message costs, which is $60. You rebill that usage to clients at whatever markup you set, and CloseBot's own documentation describes agencies billing anywhere from $100 to five figures per client per month. The subscription stops looking like software cost and starts looking like a cost of goods sold.

On the business track the math is simpler but less flexible. Core at $64 includes 500 messages with no per-message charge, so a solo business running a few hundred conversations a month pays $64 plus the GoHighLevel subscription underneath. You do not get the client portal, white labelling, or rebilling tools, which is the whole reason the agency tier exists.

Either way, remember that CloseBot is the second invoice. If you are not already on GoHighLevel, budget for that too.

## Discounts, trials, and the fine print

CloseBot publishes exactly one code of its own: `CLOSEBOT100OFF` takes $100 off your first payment. It applies on the plans page or under Settings → Subscription inside your account, and it works on both business and agency plans. Third-party partner codes do exist, but expired ones are everywhere, and the company is direct about the fact that a code changes price, not features.

The rest of the fine print is worth reading before you buy:

- Every paid plan includes a 7-day trial before you are billed.
- The free plan is free forever as long as you stay at or under 100 messages a month, and overage can be paid as you go at $0.08 per message.
- There are no refunds. The trial and the free plan exist so you can decide at zero risk instead of asking for money back.
- Plans are month to month with no contract, so upgrading, downgrading, or cancelling is straightforward.
- The free tier is a testing tier. Third-party reviews note it caps job flows to a handful of actions and limits AI provider access, and live chat support is locked on free accounts.

Ready to test it against your own lead flow rather than someone else's screenshots? 👉 [Grab the free plan and $100 off your first paid month](https://app.closebot.com/a?fpr=li87).

## When the native GoHighLevel bot is the better call

Nothing here means Conversation AI is a bad product. It is improving, it is included in your CRM, and for a straightforward FAQ-and-booking bot on one or two locations, it is often enough.

Built-in AI tends to be the right choice when you want one vendor, one invoice, and one support channel; when your conversations are simple and rarely branch; when one bot per sub-account is sufficient and each books to a single calendar; and when you are not reselling AI to clients.

The third-party route starts to win when conversations branch by service, lead type, or urgency; when you need several agents listening to different channels or tags inside the same sub-account; when you want an email channel and multi-provider fallback; and when the AI is the product you sell, which makes white labelling and rebilling non-negotiable.

## The parts people complain about

A few honest limits, drawn from documentation and third-party reviews rather than any one vendor's marketing:

- **There is a learning curve.** The drag-and-drop builder is friendlier than writing prompts, but one review scored setup effort 3 out of 5 and estimated five to ten hours of initial configuration. Templates shorten that, they do not eliminate it.
- **The CRM dependency is real.** If you do not already run GoHighLevel or HubSpot, you are buying two products. Solo operators whose whole pipeline is Instagram DMs should look at DM-native tools first.
- **Knowledge base maintenance is ongoing.** Answer quality depends on the documents you feed the agent. Nobody updates them for you.
- **High-ticket negotiation is still a human job.** These agents qualify, handle routine objections, follow up, and book. They do not draft custom proposals or close a six-figure deal.

## Common questions

**Does CloseBot work with Instagram and WhatsApp?** Only through your CRM. If those channels are connected to your GoHighLevel Conversations inbox, CloseBot can answer them. It has no standalone social messaging connection of its own.

**Can I run it on more than one sub-account?** Yes. Unlimited account connections are included even on the free plan, and one agent can serve unlimited accounts within a single niche.

**What happens when the AI does not know an answer?** Smart FAQ flags the conversation and notifies you. You supply the answer once, and the system can follow up with everyone who asked it.

**Do I need to be technical to set this up?** No developer is required. The connection is OAuth, the flow builder is drag-and-drop, and the booking node takes a calendar ID. You do need someone willing to test and iterate.

**Is there a cheaper way to try before paying?** Yes. The free plan needs no card, and the 7-day trial on paid plans runs before the first charge. Applying `CLOSEBOT100OFF` at checkout takes $100 off the first payment. 👉 [Start with the free plan here](https://app.closebot.com/register?fpr=li87).

## Bottom line

For a GoHighLevel user, the decision is not really about which chatbot writes friendlier messages. It is about architecture and arithmetic. If your conversations are simple and your locations are few, the native Conversation AI is the cheaper, simpler answer, and a $50 to $97 per-location bill is easy to justify.

If AI-set appointments are the product you sell, or you are running several sub-accounts with branching qualification logic, a dedicated agent layer with rebilling built in usually pays for itself the moment you land one client on it. Connect a sub-account, run a real lead through it on the free plan, and see whether the bookings justify the second invoice. 👉 [Wire CloseBot into your GoHighLevel account](https://app.closebot.com/a?fpr=li87)
