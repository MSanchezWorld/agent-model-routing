# World Report entry page drafts

Updated: 2026-09-23. **Copy and routing specification, not live URLs.** Do not send traffic to these paths until they are implemented and published. All pages feed one master Miguel Sanchez World Report publication.

## Shared behavior

- Email and first name at signup; do not require interest selection before capture.
- Button: **Get the Weekly Report**.
- Explain the weekly general issue plus the chosen topic. Provide working privacy and unsubscribe/preference information.
- After signup, show **Customize your World Report** with the optional checkbox interests and single-choice audience question in [AUDIENCE_ROUTING.md](AUDIENCE_ROUTING.md). New subscribers who choose no interests get the broad weekly issue. An explicit empty preference save clears topic preferences; leaving an existing preference page without saving makes no change. Confirm the provider's empty-response behavior before activation.
- Capture the actual incoming UTMs. Store the page identifier separately; do not replace `youtube` with `stack` because the visitor chose Stack.
- Store consent wording/version, timestamp, and the choice through the supported private system. Do not put identity or consent data in public URLs.

## `/newsletter/agv`

**Get the next AI video benchmark before it disappears into the feed.**

Follow the race to commercially reliable AI video. Get benchmark results, model experiments, production budgets, and the costs behind the clips, plus one short Miguel Sanchez World Report each week.

Page identifier: `agv`. Disclosed topic interest: `interest_agv_navo`.

## `/newsletter/wheelos`

**Get the weekly lead-to-cash field note for agencies.**

See what I’m learning about lead follow-up, conversion, booked calls, and collected revenue, plus one short Miguel Sanchez World Report each week.

Page identifier: `wheelos`. Disclosed topic interest: `interest_wheelos`.

## `/newsletter/stack`

**Get the Protected BTC & ETH Treasury Brief.**

Field notes on Bitcoin and Ethereum treasury decisions, leverage mechanics, and risk controls, alongside the weekly Miguel Sanchez World Report.

**Capital is at risk. “Protected” is the brief’s name, not a guarantee that your assets or returns are protected.**

Keep the Stack opt-in separate and unchecked:

> Yes, send me the Stack BTC & ETH treasury brief, including treasury education and product updates. I understand I can withdraw this choice at any time.

If unchecked, subscribe only to the clearly disclosed general World Report; do not apply Stack marketing consent or route Stack sends. Offer-specific promotions remain subject to country eligibility and review. Selecting Stack as an interest in the general survey is a preference, not a substitute for this separate consent record.

Draft risk explanation:

> This material is educational and does not provide personal investment, tax, or legal advice. BTC and ETH can lose substantial value. Borrowing against crypto can magnify losses and lead to margin calls, liquidation, and loss of collateral. Rates, custody, providers, and applicable rules introduce additional risks. Product availability and eligibility vary by country.

Page identifier: `stack`. Topic preference: `interest_stack`; send permission requires the separate consent record. Worldwide is the intended editorial audience. This draft is not a jurisdiction-approved financial promotion, and a disclosure does not establish authorization to offer products globally. For example, the [FCA's cryptoasset marketing guidance](https://www.fca.org.uk/firms/cryptoassets/marketing-uk-consumers) can apply to firms marketing to UK consumers from overseas. Obtain the applicable review before activating product promotions.

## Placement and campaign examples

Once the pages are live, keep `utm_source` tied to the actual publisher and `utm_content` tied to a real placement:

- YouTube → AGV page: source `youtube`, medium `video`, campaign `world_report`, content the actual episode/placement slug.
- WheelOS website → WheelOS page: source `wheelos`, medium `website`, campaign `world_report`.
- Stack website → Stack page: source `stack`, medium `website`, campaign `world_report`.
- Public talk → relevant page: source `public_speaking`, medium `qr`, campaign the actual event slug.
- GitHub guide → existing World Report signup: retain `github / repository / agent_routing / readme_primary`; offer AI agents among the post-signup preferences.

Do not add new hosted paths to the public README until a published page exists and its actual signup routing has been checked with authorization.
