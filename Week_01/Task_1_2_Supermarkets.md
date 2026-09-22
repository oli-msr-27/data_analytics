# Use Case 2: Demand and supply for supermarkets in Swiss municipalities

**Focus:** Supermarket chain management's perspective (expansion planning)

## Task 1 – Business Objectives and Hypotheses

1. **Problem definition**
   Supermarket chain management lacks a clear, data-driven view of which Swiss
   municipalities are currently under-served relative to their population (i.e. high
   demand but low supply of supermarkets), making it hard to identify promising
   locations for new store openings.

2. **Objective**
   Develop an analysis that identifies which Swiss municipalities are under-served with
   supermarkets relative to their population, so that supermarket chain management can
   identify promising locations for new store openings.

3. **Research question**
   Which Swiss municipalities have a low ratio of supermarkets to population (i.e.
   potential undersupply relative to demand)?

4. **Hypothesis**
   Larger municipalities (by population) have a better (higher) supermarket-to-population
   ratio than smaller, rural municipalities — i.e. smaller municipalities are more likely
   to be underserved relative to their population.

5. **Expected added value of the data analysis**
   Supermarket chain management gains a data-driven basis for site-selection decisions,
   reducing the risk of investing in saturated markets while identifying high-potential,
   underserved municipalities for expansion — giving a competitive advantage in growth
   strategy.

## Task 2 – Proposed Data

**From OpenStreetMap (supermarket data):**
- Location (latitude/longitude of each supermarket)
- Municipality — either tagged directly or derived by mapping coordinates to
  municipality boundaries
- Shop type/brand (OSM `shop=supermarket` tag, plus `name`/brand, e.g. Migros, Coop,
  Denner — useful to distinguish discounters from larger stores)
- Count of supermarkets per municipality — *derived* aggregate, computed by counting how
  many OSM supermarket points fall within each municipality

**Municipality-level data (SFSO "Regionalporträts 2021: Kennzahlen aller Gemeinden"):**
- Population per municipality — needed to compute the supermarket-to-population ratio
  (the core demand-side metric)
- Tax rate, population density — optional, to help explain *why* some municipalities are
  underserved, not just identify that they are
