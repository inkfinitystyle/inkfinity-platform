# AI Suggestions Layer – Inkfinity Platform

This document defines how AI assists during onboarding by suggesting
missing or improved links. Suggestions are optional and never auto-published.

---

## Principles

1. Suggestions are recommendations, not actions
2. Business owners always approve before publishing
3. AI fills gaps, it does not replace user intent
4. The hub must be publishable without AI

---

## When AI Is Triggered

AI suggestions are triggered if any of the following are missing:
- Website
- Google Reviews link
- Primary social link
- WhatsApp or contact method

AI is also triggered if:
- URLs look invalid or incomplete
- Brand tone is unclear
- Industry is “Other” with no notes

---

## Inputs to AI

AI may use:
- Business name
- Industry
- Location
- Provided website or social links
- Public web presence (search results)

AI must NOT:
- Guess private contact details
- Create payment links
- Publish content automatically

---

## Suggested Outputs (Examples)

### Website missing
Suggestion:
“Would you like to link your Instagram as your main page for now?”

### Google Reviews missing
Suggestion:
“Here’s your Google Business Profile search link. Add reviews to build trust.”

### Social links missing
Suggestion:
“We found these public profiles. Would you like to add one?”

---

## Suggestion Types

Each suggestion includes:
- suggestion_id
- reason
- suggested_value
- confidence_level (low / medium / high)
- requires_confirmation (always true)

---

## Confirmation Flow

1. Suggestion is shown in onboarding summary
2. User can:
   - Accept
   - Edit
   - Reject
3. Only accepted suggestions are applied to the hub

---

## Future Enhancements (Optional)

- Industry-specific defaults (e.g. food, fitness, trades)
- Suggest best CTA based on industry
- Suggest button ordering based on conversion data
