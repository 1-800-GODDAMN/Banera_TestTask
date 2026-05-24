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

1. **Entry** → Taps "+" on home screen → "Calculate a Dish."
2. **Add ingredients**:
   - Search or scan each ingredient (e.g., "spaghetti, raw 200g", "olive oil 2 tbsp").
   - Optional: paste a recipe URL → auto-extract ingredients.
3. **Set servings** → Enter number of servings the dish makes (e.g., 4).
4. **Review** → App shows total calories, kcal/serving, and macro breakdown.
5. **Save** → Option to save as "My Dish" for one-tap logging later.
6. **Log** → "Add to today" → choose meal (breakfast/lunch/dinner/snack).

**Success criteria**: Complete in under 60 seconds for a 5-ingredient dish.

---

### Flow 2 — Find a Suitable Recipe

**Goal**: Maria has 600 kcal left for dinner and wants a recipe idea.

1. **Entry** → Home screen shows "Remaining today: 600 kcal" → tap "Find a recipe."
2. **Set constraints** (pre-filled from context):
   - Calorie range: 400–600 kcal (auto-set from remaining budget).
   - Optional filters: meal type, prep time, dietary restrictions, ingredients on hand.
3. **Browse results** → Ranked list of recipes with thumbnail, kcal, prep time, macro tags.
4. **Preview** → Tap a recipe → see ingredients, steps, full nutrition per serving.
5. **Choose action**:
   - "Cook this" → adds to today's log + saves to meal plan.
   - "Save for later" → adds to favorites.
   - "Adjust servings" → recalculates calories live.
6. **Confirm** → Recipe logged, remaining calories updated on home screen.

**Success criteria**: From "find a recipe" tap to logged meal in under 90 seconds.
