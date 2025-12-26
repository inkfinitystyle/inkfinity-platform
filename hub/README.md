# Inkfinity Hub – Structure

This folder defines what an Inkfinity Hub is and how it behaves once published.

A Hub is the end result of onboarding:
• One QR code
• One landing page
• Multiple destinations (links, actions, payments, reviews)

The goal is to remove friction for customers and complexity for businesses.

---

## Core Components of a Hub

Every hub consists of:

1. Metadata
2. Branding
3. Buttons (destinations)
4. QR behaviour
5. Analytics (later phase)

---

## 1. Metadata

Required:
- hub_id (unique)
- business_name
- created_at
- status (draft | active | paused)

Optional:
- industry
- location
- notes (internal)

---

## 2. Branding

Branding is lightweight by design.

Optional branding fields:
- primary_color
- secondary_color
- logo_url
- brand_tone

Rules:
- If no branding is provided, use Inkfinity default theme
- Branding must never block hub creation

---

## 3. Buttons (Destinations)

A hub displays a vertical list of buttons.

Each button has:
- id
- label
- type (link | whatsapp | payment | review | social)
- destination (URL or action)
- priority (number)

Rules:
- Only include buttons with valid destinations
- Sort buttons by priority (lowest = top)
- Maximum default buttons: 6
- Extra links can be collapsed under “More”

---

## 4. QR Behaviour

Each hub has:
- One permanent QR code
- QR always points to the hub URL
- Destinations can change without reprinting QR

Rules:
- QR must never break once issued
- Old hubs redirect if upgraded or replaced

---

## 5. Default Hub Rules

A hub must:
- Load fast
- Work without login for customers
- Be mobile-first
- Require zero explanation to use

A hub must NOT:
- Show ads
- Require an app download
- Require account creation for customers

---

## Hub Lifecycle

1. Created (draft)
2. Reviewed (optional)
3. Published (active)
4. Updated (links change, QR stays)
5. Paused or archived

---

## Future Enhancements (not MVP)

- Analytics dashboard
- Button click tracking
- A/B button ordering
- Multiple hubs per business
