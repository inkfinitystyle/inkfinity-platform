# Onboarding Data → Hub Build Schema

This document explains how onboarding answers become a usable Inkfinity Hub.

## Inputs
Onboarding data is collected using:
- `onboarding/questions.json`

Each submission should be stored as a single JSON object (an “onboarding submission”).

## Output
A hub is generated with:
- A title (business name)
- Optional brand styling (colors / tone)
- A set of buttons/links in a sensible order
- A primary call-to-action based on the business goal

## Normalisation Rules (cleaning data)
1. Trim whitespace on all text fields
2. Convert empty strings to `null`
3. Ensure URLs start with `https://`
4. For WhatsApp number:
   - Store as E.164 if possible (e.g. +353...)
   - If not, store raw and flag for manual review

## Link Priority (default order)
When building a hub, buttons are ordered like this (only include if provided):
1. Main goal CTA (based on `cta_goal`)
2. Website / Booking / Shop (menu_or_booking_url)
3. Google Reviews
4. WhatsApp
5. Instagram
6. Facebook
7. TikTok
8. Payment link

## CTA Goal Mapping
`cta_goal` determines the “top button” label and which link is preferred.

- Get more enquiries
  - Prefer: WhatsApp number
  - Label: “Message us”
- Get more reviews
  - Prefer: Google Reviews link
  - Label: “Leave a review”
- Get more bookings
  - Prefer: menu_or_booking_url (booking page)
  - Label: “Book now”
- Get more sales
  - Prefer: menu_or_booking_url (shop link) OR payment_link
  - Label: “Shop now”
- Grow social following
  - Prefer: Instagram OR TikTok (whichever is provided first)
  - Label: “Follow us”
- Other
  - Prefer: website_url
  - Label: “Visit our website”

## AI Suggestions (future)
If key links are missing, AI can suggest likely targets by using:
- Business name
- Industry
- Public web presence (website + social)
Examples:
- If no Google Reviews link is provided, suggest the Google Business Profile search URL.
- If no website is provided, suggest Instagram as the hub’s “home”.

AI suggestions must be presented as optional recommendations, never auto-published without confirmation.

## Validation & Manual Review Flags
Flag for manual review if:
- No link fields were provided at all
- More than 2 URLs fail va
