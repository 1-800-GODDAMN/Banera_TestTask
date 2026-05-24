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

### Flow 1 — Calculate Calories in a Dish

**Goal**: Maria cooked a homemade pasta dish and wants to know the calories per serving.

1. **Entry** → Taps "Calculate a dish" action card on Home screen.
2. **Add ingredients**:
   - Search each ingredient (e.g., "spaghetti, raw 200g", "olive oil 2 tbsp").
   - Adjust quantity inline with per-ingredient calorie feedback as you go.
   - Optional: pick from "Browse saved dishes" for one-tap entry of a previously saved meal.
3. **Set servings** → Enter number of servings the dish makes (e.g., 4). The total card updates live, showing kcal per serving.
4. **Calculate** → Tap "Calculate dish" to see the full result: dish name, kcal per serving, total kcal, and macronutrient breakdown.
5. **Log** → "Add to today" → meal is logged and Home updates with new remaining calories. Optional: "Save as my dish" for future one-tap logging.

**Success criteria**: Complete in under 60 seconds for a 5-ingredient dish.

**Note on consolidation**: The original spec included a separate "Review" step between Add ingredients and the result. I merged it into Add Dish — per-ingredient kcal and live total now appear on the same screen as the input. Fewer screens, same information, faster flow. The "Calculate dish" CTA then takes the user directly to the final result with macros and logging actions.

---

### Flow 2 — Find a Suitable Recipe

**Goal**: Maria has 1,000 kcal left for the day and wants a recipe idea for dinner.

1. **Entry** → Home screen shows "1,000 kcal remaining today" → tap "Find a recipe" action card.
2. **Set constraints** (pre-filled from context):
   - Calorie target: shown in a context card ("Showing recipes under 600 kcal") — automatically scaled to her remaining budget.
   - Optional filters: dietary restrictions (Vegetarian, Vegan), prep time (Quick), nutrition (High protein, Under 600 kcal). Two filters are pre-selected based on Maria's profile.
3. **Browse results** → Ranked list of 5 recipes with category icon (fish, stew, bowl, salad, stir-fry), kcal per serving, prep time, dietary tags.
4. **Preview** → Tap a recipe → Recipe Detail shows nutrition per serving (kcal + protein/carbs/fat), ingredients list, and a collapsed "Instructions · 4 steps" section.
5. **Choose action**:
   - "Add to today" → adds to today's log and returns to Home with updated remaining calories.
   - "Save for later" → adds to favorites.

**Success criteria**: From "Find a recipe" tap to logged meal in under 90 seconds.
