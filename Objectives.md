# Objective

## Problem

Finding a flat to rent in London is highly competitive. Good properties are often
let within hours of being listed, sometimes before viewings can even be booked.

The listings are spread across several property websites. Each site has its own
search filters, alert system and notification timing. Keeping up in real time means:

- Checking several websites manually, many times a day.
- Relying on native email alerts, which are often delayed (sometimes by hours)
  or grouped into daily digests.
- Seeing the same property more than once because it's cross-listed on several sites.
- Missing new listings while at work, asleep or busy.

**As a result, I often find out about a suitable flat too late, after it has
already been taken or the viewing slots are full.**

## Solution

Build an **AI agent that watches the 4 most common London housing websites and
sends me live notifications** as soon as a property that matches my criteria is listed.

### Target websites

1. **Rightmove**
2. **Zoopla**
3. **OpenRent**
4. **SpareRoom**

### What the agent will do

1. **Monitor continuously.** Poll each website at short intervals
   (e.g. every 2–5 minutes) for new listings.
2. **Apply my search criteria.** Filter by:
   - Location / postcodes / areas (e.g. zones, boroughs, distance from a station)
   - Price range (monthly rent)
   - Number of bedrooms
   - Property type (flat, studio, house share…)
   - Optional extras (furnished, pets allowed, available-from date, bills included)
3. **Detect new properties.** Keep a record of listings already seen so that I'm
   only notified about genuinely new ones.
4. **Deduplicate across sites.** Recognise when the same property appears on
   several websites (matching on address, price, photos or description) and
   send a single alert for it.
5. **Send live notifications.** Push an alert immediately (e.g. via Telegram,
   email, SMS or a mobile push notification) that contains:
   - Title, price, location and number of bedrooms
   - Main photo
   - Source website and a direct link to the listing
   - Time it was listed
6. **Summarise and rank (AI layer).** Use an LLM to give each listing a short
   summary and a match score against my preferences, so I can decide quickly
   whether to act on it.

### Success criteria

- I'm notified about a new matching listing **within 5 minutes** of it being published.
- **All 4 websites** are covered from one place.
- **No duplicate alerts** for the same property.
- **Few false positives.** Alerts match my criteria.
- Fewer hours spent manually searching each day, and more viewings booked early.

### Out of scope (for the first version)

- Contacting landlords or agents, or booking viewings automatically.
- Websites other than the 4 listed above.
- Buying (sales) listings. Rentals only.
