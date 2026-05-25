# Calories Calculator — Research

## 1. Competitor Analysis

### MyFitnessPal
- **Strengths**: Massive food database (14M+ items), barcode scanner, large community, recipe importer from URLs, integrations with fitness trackers.
- **Weaknesses**: Aggressive paywall (barcode scan, macro goals locked behind Premium), cluttered UI, user-submitted data often inaccurate.
- **Target user**: Mainstream dieters and weight-loss focused users.
- **Monetization**: Freemium ($19.99/mo Premium).

### Cronometer
- **Strengths**: Curated, verified nutrient database (NCCDB), tracks 80+ micronutrients, accurate macro/micro breakdowns, popular with biohackers and clinical users.
- **Weaknesses**: Steeper learning curve, less social/community, smaller food database, UI feels utilitarian.
- **Target user**: Health-conscious users, athletes, low-carb/keto, medical diets.
- **Monetization**: Freemium ($8.99/mo Gold).

### Lose It!
- **Strengths**: Clean onboarding, "Snap It" photo food recognition, simple goal-setting, gamified streaks and challenges.
- **Weaknesses**: Photo recognition often inaccurate, smaller verified database, fewer micronutrient details.
- **Target user**: Casual users wanting simple weight tracking with minimal friction.
- **Monetization**: Freemium ($39.99/yr Premium).

### Key Takeaways
- Database accuracy + speed of logging are the two biggest differentiators.
- Photo/AI-based recognition is the emerging frontier (still unreliable).
- Recipe discovery is underserved — most apps focus on logging, not meal planning around calorie/macro targets.

---

## 2. UX Persona

### Maria, 32 — "The Busy Optimizer"
- **Role**: Marketing manager, mother of one.
- **Tech**: Heavy iPhone user, comfortable with apps but low patience for friction.
- **Goal**: Lose 5 kg while maintaining energy for work and family.
- **Behaviors**: Cooks dinner 4x/week, eats out 2x/week, snacks at her desk.
- **Pain points**:
  - Hates manually entering every ingredient of a homemade dish.
  - Doesn't know what to cook that fits her daily calorie budget.
  - Gets discouraged when logging takes more than 30 seconds.
- **Needs**:
  - Fast, accurate calorie calculation for home-cooked dishes.
  - Recipe suggestions that match her remaining daily calories.
  - Minimal data entry, smart defaults, trustworthy numbers.
- **Quote**: *"I just want to know if this meal fits — not fill out a form."*

---

## 3. User Flows

### Flow 1 — Calculate calories in a dish

**Goal**: Maria wants to log a dish — either one she's saved before, a known public recipe, or something she's built from scratch.

The Home screen offers two entry points reflecting Maria's preference for fast paths over manual entry:

#### Path A — Log a saved or public dish (fast path)

1. **Entry** → Home → tap "Log a dish".
2. **Search or browse** → Saved dishes appear by default. Tap the search bar to find a public recipe (e.g. "spag" → Spaghetti Carbonara).
3. **Select** → Tap the dish → opens the edit screen with all ingredients pre-filled.
4. **Adjust** → Edit ingredient quantities with inline steppers if needed (e.g. used 250g spaghetti instead of 200g). Total calories recalculate live.
5. **Log** → Tap "Add to today".

**Success criteria**: From Home to logged meal in under 30 seconds for a saved dish.

#### Path B — Build from scratch (manual path, fallback)

1. **Entry** → Home → tap "Build a dish".
2. **Empty state** → Edit screen opens with no ingredients. Empty state placeholder invites first add.
3. **Add ingredients** → Tap "+ Add ingredient" → bottom sheet slides up with ingredient suggestions. Tap an ingredient (e.g. Tomato) → quantity stepper with live calorie preview → "Add to dish".
4. **Repeat** → Continue adding ingredients one by one until the dish is built.
5. **Name & set servings** → Optionally name the dish, adjust servings count.
6. **Log** → Tap "Add to today".

**Success criteria**: From Home to logged dish in under 60 seconds for a 5-ingredient dish.

**Design rationale**: Maria's stated pain point is "hates manually entering every ingredient." Two paths respect that — the fast path (Log) handles 90% of common cases (repeated meals, known recipes), while the manual path (Build) remains available for genuine new dishes. The system never forces manual entry as the primary flow.

---

### Flow 2 — Find a suitable recipe

**Goal**: Maria has remaining calories for the day and wants a recipe idea that fits her budget and preferences.

1. **Entry** → Tap "Search" in the tab bar.
2. **Context** → Recipe Finder shows "1,000 kcal remaining → Showing recipes under 600 kcal" — pre-filtered to her actual remaining budget.
3. **Refine filters** → Optional filter chips: dietary tags (Vegetarian, Vegan, High protein), prep time (Quick), calorie ceiling.
4. **Browse results** → Ranked list of recipes with category icon, prep time, dietary tags, kcal.
5. **Preview** → Tap a recipe → ingredients list + collapsible instructions + full nutrition breakdown (calories + macros per serving).
6. **Choose action**:
   - **Cook this** → adds to today's log → returns to Home with updated calorie count.
   - **Save for later** → toggles saved state (bookmark fills sage). Recipe is now reachable via the Saved tab.

**Success criteria**: From Search tap to logged or saved recipe in under 90 seconds.

**Design rationale**: Recipe discovery is a separate mental mode from calorie logging — prospective ("what should I cook") vs retrospective ("what did I eat"). Recipe Finder lives in the tab bar as a top-level discovery surface, not nested under Home, to honor that distinction. Stateful Save toggle lets Maria collect candidates without committing — she can plan tonight's dinner while browsing without logging it now.

---

## 4. Out of MVP Scope

These elements would be addressed in iteration 2:

- **Onboarding flow** — calorie target calculation via Mifflin-St Jeor formula based on user demographics. Current prototype uses static demo target (2,000 kcal).
- **Real ingredient database** — USDA nutrition data integration for accurate kcal per 100g. Current prototype uses fake suggestion data.
- **Saved recipes tab destination** — full screen for managing saved recipes (currently placeholder in tab bar).
- **Stats tab destination** — long-term tracking visualizations (currently placeholder in tab bar).
- **Meal type assignment on log** — choosing breakfast/lunch/dinner/snack at log time (currently auto-assigned).
- **Edit history** — undo/redo on logged meals.
