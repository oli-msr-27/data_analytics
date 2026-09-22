# Use Case 1: Price prediction model for rental apartments in the canton of Zürich

**Focus:** Tenant's perspective

## Task 1 – Business Objectives and Hypotheses

1. **Problem definition**
   Tenants searching for apartments in the canton of Zürich have no easy way to judge
   whether an offered rental price is fair relative to the market, given the apartment's
   characteristics (size, rooms, location, etc.). This creates information asymmetry —
   landlords/agents know the market, tenants often don't.

2. **Objective**
   Develop a model that predicts the expected/fair rental price of an apartment in the
   canton of Zürich based on its characteristics (e.g. size, rooms, location), so that a
   tenant can compare a listing's asking price against the predicted price to judge
   whether it's over- or under-priced.

3. **Research question**
   Can apartment characteristics such as size (living space, number of rooms), location
   (distance to Zürich city center), and building age be used to predict the rental price
   of an apartment in the canton of Zürich?

4. **Hypothesis**
   Rental apartments with a larger living space, a greater number of rooms, a shorter
   distance to Zürich city center, and a newer building age have a higher rental price
   than apartments with smaller living space, fewer rooms, greater distance to the city
   center, and older building age.

5. **Expected added value of the data analysis**
   Tenants gain an objective, data-driven benchmark to assess whether a listed rental
   price is fair, helping them avoid overpaying and giving them concrete reasoning (a
   predicted "fair price") to support negotiations with landlords or agents. This reduces
   the information asymmetry between tenants and the market.

## Task 2 – Proposed Data

**From listing data (immoscout24.ch):**
- Location (address)
- Number of rooms
- Size (living space)
- Price
- Age of building
- Age of listing (how long it's been on the market) — secondary/nice-to-have variable
- Distance to Zürich city center — *derived* by geocoding the address and calculating
  distance to a reference point (e.g. Zürich HB), not a raw field from the listing

**Municipality-level data (SFSO "Regionalporträts 2021: Kennzahlen aller Gemeinden"),
used to supplement/enrich the listing data:**
- Tax rate
- Population density
- Urban vs. rural classification
- Amenities (number of schools, hospitals, etc.)

These municipality-level indicators serve as proxies for location quality/attractiveness,
supporting the "location" part of the hypothesis beyond just raw distance to the city
center.
