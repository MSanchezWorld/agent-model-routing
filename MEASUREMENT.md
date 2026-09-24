# Measurement and attribution

## What this guide can prove

Routing recommendations and commercial attribution answer different questions. Newsletter signups or audit purchases do **not** prove that a model route saves tokens or money. A savings claim needs comparable tasks, the same acceptance criteria, observed usage, retries, and complete task cost. Missing data stays unknown.

## Reader path

GitHub guide → World Report signup → relevant email → optional AI workflow audit.

The primary newsletter link uses `utm_source=github`, `utm_medium=repository`, `utm_campaign=agent_routing`, and `utm_content=readme_primary`. The secondary direct audit link uses the same source/medium/campaign and `utm_content=readme_audit`.

The welcome email's audit link uses `utm_source=msw_report`, `utm_medium=email`, `utm_campaign=agent_routing`, and `utm_content=welcome_audit`. This identifies the email placement. It does not carry the subscriber's original acquisition source or identity across websites.

Campaign values describe a placement, never a person. Do not add email addresses, names, customer IDs, API keys, or private project names to public URLs.

The [audience routing contract](AUDIENCE_ROUTING.md) separates acquisition source, selected interests, self-reported audience type, and confirmed product events. A GitHub acquisition does not imply Navo interest. A Stack booking does not imply a Navo purchase. Preserve product and consent scope when attributing outcomes.

## Reports to keep separate

| Question | Evidence | Limit |
| --- | --- | --- |
| How many people viewed the repository? | GitHub traffic report | Aggregate traffic; not a subscriber identity or revenue report |
| Which signups came from the guide? | Beehiiv subscriber acquisition fields for `github / repository / agent_routing` | Attribution can be absent or affected by an existing subscription or a different journey |
| Which emails generate interest in an audit? | Beehiiv tracked clicks on the audit link | A click is not a booking or payment; scanners can create clicks |
| Which audits were paid? | Successful, verified payment records, with refunds separately recorded | A checkout view, thank-you page, or CRM stage alone is not payment proof |
| Did a guide-acquired subscriber later buy? | A private match between subscriber acquisition and confirmed audit payment | An observed association, not proof the guide caused the sale |

Beehiiv documents [website subscriber attribution](https://www.beehiiv.com/support/article/42701649665559-understanding-subscriber-attribution-from-your-website) and [email UTM tagging](https://www.beehiiv.com/support/article/14492992521367-Using-UTM-parameter-tracking-with-beehiiv). GitHub documents its [repository traffic reports](https://docs.github.com/en/repositories/viewing-activity-and-data-for-your-repository/viewing-traffic-to-a-repository).

## Private revenue reconciliation

Use the existing email and payment platforms. A periodic export audit needs no additional tracking pixel or paid service.

1. Export subscriber acquisition fields from Beehiiv and confirmed audit payments for the chosen reporting window. Keep both files private. Record export time, timezone, window, and the payment product used to select audit purchases.
2. Match trimmed, case-normalized email addresses privately. Do not remove `+tags`, dots, or guess aliases. Flag conflicting subscriber records and unmatched payments for review; never infer an identity from a name alone.
3. Preserve subscriber acquisition source and the later audit interaction source in separate columns. A newsletter link must not be relabeled as a GitHub click.
4. Count distinct subscribers and distinct successful payment IDs. Include only payments on or after signup when describing a subscriber-to-customer journey. Keep currencies separate and subtract recorded refunds when reporting net receipts. A missing refund value is unknown, not zero.
5. Report matched receipts, unmatched receipts, refunds, and coverage. Zero is meaningful only for a complete observation window. Do not count sample/template rows as real results.
6. Publish aggregate findings only after review. Keep customer details, raw exports, and payment identifiers out of this repository and all public issues.

This is a periodic reconciliation procedure. It is not a claim that an automatic subscriber-to-payment integration is deployed or that a paid conversion has been verified.

When reporting by interest or avatar, record whether the value was known at signup or changed later. Keep unknowns visible; do not backfill historical cohorts using today's preferences. Count people once within a cohort, and do not sum overlapping topic audiences as if they were distinct people. Report contribution, waitlist, booking, and purchase separately rather than inventing a universal intent score.

## Agent boundaries

Agents may read the routing guide without subscribing or clicking commercial links. Do not insert promotions into another user's work. Maintaining this file does not authorize exports, new tracking, email sends, paid upgrades, or payment operations; follow the owner's current instructions and account permissions.
