# BuySooner Roadmap v2

This repository contains the working BuySooner broker/customer prototype and the staged build of the generated BuySooner Roadmap.

## Current purpose

The project is intended to work as one connected flow:

1. The broker/customer prototype captures customer and property information.
2. The prototype stores that information in a structured roadmap data object.
3. The roadmap pages are rendered from that stored data.
4. Each roadmap page is added and tested one page at a time.

The first priority is data capture, not visual roadmap pages.

---

## Repository structure

Expected files:

- index.html
- i1.jpg
- README.md

### index.html

The main working prototype.

It should contain:

- the broker/customer journey
- input screens
- calculations
- navigation
- roadmap data capture layer
- future roadmap page screens

### i1.jpg

Image used on Roadmap Page 1.

Future roadmap images should follow the same naming convention:

- i1.jpg
- i2.jpg
- i3.jpg
- and so on

---

## Build approach

The roadmap should not be built as a disconnected standalone report.

The correct approach is:

Prototype data capture → central roadmap data object → roadmap page rendering

The prototype remains the source of truth for customer information.

---

## Stage 1 — Data capture layer

Before building Roadmap Page 1, the prototype must generate a clean data object.

The object should capture the following.

### Customer

- customer name
- renter or upgrader status
- dependants
- income details

### Property

- target suburb
- property address, if supplied
- target purchase price
- current property details, if upgrader

### Finance

- customer contribution
- current rent or housing cost
- living expenses
- debts
- credit card limits
- estimated bank loan
- BuySooner Boost

### Broker

- broker name
- broker firm
- broker email
- broker phone

### Assumptions

- market growth assumption
- refinance window
- target refinance LVR
- mortgage rate assumptions, if used

### Derived values

- deposit gap
- total deposit position
- starting deposit percentage
- estimated senior loan
- indicative refinance pathway figures

---

## Proposed data functions

The prototype should include functions similar to:

- collectRoadmapData()
- calculateRoadmapDerived()
- saveRoadmapData()
- loadRoadmapData()

The saved data should be available in:

- window.BuySoonerRoadmapData
- localStorage.BuySoonerRoadmapData

---

## Stage 2 — Test captured data

Before adding Roadmap Page 1, the final prototype screen should allow the captured data to be checked.

Testing should confirm:

| Field | Required behaviour |
|---|---|
| Customer name | Pulls the actual entered name |
| Buyer type | Correctly identifies renter or upgrader |
| Suburb/address | Pulls the entered suburb or address |
| Target price | Pulls and formats correctly |
| Contribution | Pulls and formats correctly |
| BuySooner Boost | Calculates or pulls correctly |
| Estimated mortgage | Calculates correctly |
| Rent/housing cost | Handles renter and upgrader cases |
| Broker details | Pulls through if entered |
| Missing values | Uses safe fallbacks |

Do not build Roadmap Page 1 until this data layer works.

---

## Stage 3 — Roadmap Page 1

Once data capture is confirmed, add Roadmap Page 1 after the final prototype screen.

The intended flow is:

Final prototype screen → Roadmap Page 1

Roadmap Page 1 should use:

- i1.jpg

It should render from the stored roadmap data, not hard-coded demo values.

---

## Roadmap Page 1 agreed design direction

Page 1 should include:

- BuySooner branding
- “Welcome home, [First name].”
- image card using i1.jpg
- dynamic renter/upgrader opening copy
- property snapshot
- strategy and assumptions
- right-aligned financial values
- footer metadata and disclaimer

The previous “Your scenario” tile should be removed and replaced with the image.

The headline should be approximately 13% smaller than the earlier mock-up.

The ownership message should read:

“This is not just about a mortgage. It is about the freedom to hang pictures, make the space your own, and build a life in a home that belongs to you — in a community you genuinely want to call home.”

---

## Renter path copy

This is your plan to move out of the rental cycle and into your own home. Based on your goal to buy in [Suburb], this Roadmap shows how BuySooner may help you bridge the deposit gap, start building equity sooner, and create a clearer pathway toward refinancing into a standard mortgage.

We have brought together your target purchase price, current contribution, estimated bank loan, BuySooner Boost and indicative refinance pathway to show how the numbers may work in practice. The figures are illustrative and subject to assessment.

---

## Upgrader path copy

This is your plan to move from your current property into a home that better fits your needs. Based on your goal to buy in [Suburb], this Roadmap shows how BuySooner may help you bridge the funding gap, move sooner, and create a clearer pathway toward refinancing into a standard mortgage.

We have brought together your target purchase price, available contribution, estimated bank loan, BuySooner Boost and indicative refinance pathway to show how the numbers may work in practice. The figures are illustrative and subject to assessment.

---

## Key principle

Do not build separate static report pages unless specifically required.

Each roadmap page should be rendered from the same shared data object created by the prototype.

The correct order is:

1. Data capture first.
2. Test data second.
3. Roadmap Page 1 third.
4. Then build each additional roadmap page one at a time.
