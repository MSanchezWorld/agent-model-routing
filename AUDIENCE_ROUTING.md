# World Report audience routing

Updated: 2026-09-23. This is the operating contract for the newsletter connected to this guide. It does not change the model routes in [ROUTING.md](ROUTING.md).

**One master publication: The Miguel Sanchez World Report.** Track acquisition, interests, audience type, consent, and product events separately. A tag is a useful label, not proof that an integration is running or that someone agreed to receive every topic.

## Implementation status

The public guide's newsletter and audit links are available. The post-signup preferences survey has been saved as a draft. Automatic tag synchronization, product-event connections, topic entry pages, and the new signup flow are not live. Keep using the existing newsletter link until the owner approves and the relevant pages are published. Never replace a working link with a proposed path from this document.

## 1. Acquisition: where they came from

Preserve Beehiiv's native acquisition source, medium, campaign, and content. Normalize a copy of an allowlisted `utm_source` for the following tags; retain the original attribution record privately.

| `utm_source` | Acquisition tag |
| --- | --- |
| `youtube` | `source_youtube` |
| `navo` | `source_navo` |
| `massideation` | `source_massideation` |
| `wheelos` | `source_wheelos` |
| `stack` | `source_stack` |
| `referral` | `source_referral` |
| `public_speaking` | `source_public_speaking` |
| `github` | `source_github` |

- The `source_*` tag describes first observed acquisition. Do not overwrite it with a later email click. Store later interactions separately with timestamps.
- Missing or unrecognized source stays unknown. A `referral` tag requires an attributable referral link or provider record; do not guess it from a missing UTM.
- Source, landing page, and interest are independent. YouTube → Stack page means `source_youtube` plus a Stack entry page; it does not mean `source_stack`.
- Store an entry page identifier such as `agv`, `wheelos`, or `stack` separately. A general GitHub reader is not automatically an AGV subscriber.
- Put campaign descriptions in URLs, never names, emails, subscriber IDs, credentials, or other private data. Campaign tags are attribution hints and must not control privileges, payment state, or consent.

Beehiiv documents [subscriber attribution](https://www.beehiiv.com/support/article/42701649665559-understanding-subscriber-attribution-from-your-website) and [UTM tracking](https://www.beehiiv.com/support/article/14492992521367-Using-UTM-parameter-tracking-with-beehiiv). Native UTM capture does not automatically create these custom tags; that mapping still needs an authorized integration or a reviewed private reconciliation.

## 2. Interests: what they want

Capture email first. Ask **What do you want more of?** after signup. Allow multiple choices and skipping. Store the selected labels in a list field named `msw_interests` and map them exactly:

| Choice | Tag |
| --- | --- |
| AI video, Navo, and AGV | `interest_agv_navo` |
| Agency lead-to-cash systems and WheelOS | `interest_wheelos` |
| Bitcoin, Ethereum, and capital leverage with Stack | `interest_stack` |
| AI agents and business systems | `interest_ai_agents` |

Use exact list membership, not substring matching. If an older `Interests` string field exists, preserve it until its actual encoding and consent context have been reviewed; do not silently migrate it by guessing delimiters.

An explicitly described topic signup can establish its topic interest. The generic signup has no blanket topic default. An explicit preference update replaces prior inferred/default interests; deselection removes the corresponding derived tag. A skipped survey leaves valid prior preferences unchanged. Preserve an explicit “none” or opt-out separately from an unanswered question so old defaults cannot return.

Record why an interest was assigned: explicit choice, disclosed topic signup, or behavioral signal. Topic clicks may create a separate dated engagement signal; they do not override a refusal or grant consent for Stack marketing. Do not use email opens as reliable intent evidence.

## 3. Audience: who they say they are

Ask **Which best describes you?** as an optional second question. Store one selection in `msw_audience_type`. It must not block email signup.

| Choice | Tag |
| --- | --- |
| Agency owner | `avatar_agency` |
| Creative or production studio | `avatar_studio` |
| Creator or filmmaker | `avatar_creator` |
| Founder or operator | `avatar_founder` |
| Investor or long-term crypto holder | `avatar_investor` |
| AI-agent builder | `avatar_agent_builder` |
| Just exploring | `avatar_exploring` |

Replace the derived avatar tag when the subscriber changes their answer. Do not infer wealth, holdings, suitability, occupation, or purchase readiness from this field. Skipping is unknown, not “Just exploring.”

## 4. Intent: what actually happened

Keep the requested summary tags, backed by a private event record. Store the product (`navo`, `wheelos`, `stack`, or `ai_workflow_audit`) on each event; a Stack customer is not automatically a Navo customer. Contributor and waitlist are separate behaviors, not compulsory steps in a linear funnel.

| Tag | Required evidence |
| --- | --- |
| `stage_subscriber` | Confirmed active newsletter subscription under the publication's consent/confirmation rules |
| `stage_engaged` | A confirmed meaningful action, such as a completed diagnostic or a human reply; document the exact rule |
| `stage_contributor` | Accepted benchmark grading/contribution record |
| `stage_waitlist` | Confirmed enrollment in the named product waitlist |
| `stage_audit_ready` | Completed diagnostic meeting the owner's documented criteria and an explicit request/permission for follow-up; criteria must be defined before automation |
| `stage_call_booked` | Confirmed booking from the scheduling system for the named product |
| `stage_customer` | Confirmed successful payment or an authoritative customer activation record, with product and status |

Examples: a confirmed Navo waitlist enrollment supports Navo interest and waitlist evidence; accepted clip grading supports Navo contribution evidence; a completed agency diagnostic supports WheelOS engagement evidence. A confirmed Stack call supports Stack booking evidence. These actions do not themselves authorize unrelated newsletter sends.

### Event contract for future integrations

Keep a private event ledger with: `schema_version`, provider event ID, event type, occurred/received times in UTC, provider, private subject reference, product, status, evidence reference, and any relevant consent version. Never publish the ledger or identifiers here.

1. Authenticate the provider event. Do not accept browser query parameters or a success-page visit as proof of payment or a booking.
2. Deduplicate by provider plus event ID. Retried deliveries must not inflate counts or repeatedly apply side effects.
3. Resolve identity using an authorized, deterministic private mapping; ambiguous or unmatched records stay unresolved. Never guess by name.
4. Apply a versioned event-to-tag rule. Keep the underlying product-specific record; summary tags are insufficient for product sales targeting.
5. Process cancellations, removals, refunds, consent withdrawals, and out-of-order events. A cancelled booking must not remain “currently booked”; a former waitlist membership must not remain current. Preserve historical events separately from current state. Refunds remain separate financial records, and paid counts/net receipts must be corrected.
6. Do not reactivate an unsubscribed or suppressed person when a new product event arrives. Consent and deliverability suppression win over all routing tags.
7. Record synchronization status and failures. A saved tag or published Markdown file is not proof that an event was received.

## 5. Send rules

| Content | Eligible audience |
| --- | --- |
| Short weekly World Report | Active, consenting, unsuppressed master publication subscribers |
| AGV/Navo benchmarks and production economics | Eligible subscribers with AGV/Navo topic preference |
| WheelOS lead-to-cash field notes | Eligible subscribers with WheelOS topic preference |
| AI agents and business systems | Eligible subscribers with AI agents topic preference |
| Stack treasury content | Eligible subscribers with Stack preference and the separate applicable consent; product promotions also require approved country eligibility |

The general issue is a short digest of what Miguel is testing. Keep detailed topic campaigns within their audiences. Deduplicate recipients within each send and coordinate frequency across overlapping interests. No send is authorized merely by this document.

Worldwide is the intended Stack editorial audience, not an assertion that a product can be offered in every country. Do not infer country from a source tag, avatar, email domain, or crypto interest. Country eligibility and offer-specific review remain separate. See [entry page copy](ENTRY_PAGES.md).

## Agent implementation and update procedure

1. Read this contract, [MEASUREMENT.md](MEASUREMENT.md), current owner instructions, and the private implementation status. Inspect current provider capabilities and plan restrictions.
2. Reuse the master publication and existing fields/tags. Do not create another list per product, duplicate tags, or mass-classify existing subscribers without evidence.
3. Prepare changes as drafts. Beehiiv [surveys](https://www.beehiiv.com/support/article/21900901004311-How-to-create-and-use-beehiiv-surveys) and [signup flows](https://www.beehiiv.com/support/article/33701445445271) are separate features; a survey draft is not a live post-signup flow. Confirm plan availability. Embedded external forms do not automatically inherit hosted signup flows.
4. After owner authorization for activation, connect the actual form/page, survey, consent, and event mappings. Preserve UTM attribution through the real supported integration. Do not fabricate API field names or assume a redirect carries identity or tags.
5. Before claiming the funnel works, obtain authorized outcome checks for acquisition capture, multiple interests, skipped questions, explicit changes, suppressed subscribers, product isolation, and replayed/cancelled/refunded events. Do not create fake subscribers or purchases in production.
6. Keep exact live/draft/blocked status and evidence in the private runbook. Update these public rules when the contract changes, with a dated changelog and rollback through Git. Do not publish private account IDs, subscriber records, credentials, or event payloads.
7. Report acquisition, engagement, confirmed commercial outcomes, and routing cost evidence separately. Missing data stays unknown. Never claim that newsletter conversions prove model cost savings.
