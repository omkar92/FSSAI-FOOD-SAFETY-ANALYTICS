# Synthetic FSSAI Food Safety Enforcement Analytics Dataset

**Important:** Every record in these files is synthetic and generated for portfolio/practice use. These are NOT official FSSAI records and must not be represented as real raids, real businesses, actual penalties, or official statistics.

## Files and grain
- `food_businesses.csv`: one row per simulated food business (500 rows).
- `food_raids.csv`: one row per simulated inspection/raid event (1,200 rows).
- `food_samples.csv`: one row per simulated food sample; a raid can have multiple samples.
- `violations.csv`: one row per simulated violation; a raid can have multiple violations.
- `enforcement_actions.csv`: one row per simulated enforcement action per raid.

## Join keys
- `food_businesses.business_id` = `food_raids.business_id`
- `food_raids.raid_id` = `food_samples.raid_id`
- `food_raids.raid_id` = `violations.raid_id`
- `food_raids.raid_id` = `enforcement_actions.raid_id`

## Main fields
- IDs are generated identifiers, not official case IDs.
- `raid_date`, `sample_collection_date`, `action_date`: ISO date format (YYYY-MM-DD).
- `estimated_fine_inr` and `fine_amount_inr`: simulated amounts in Indian rupees; they are not legally assessed fines.
- `lab_result`: Compliant, Non-Compliant, or Inconclusive.
- `detected_issue`: simulated test issue; “None Detected” is used for compliant samples.
- `licence_status`, `risk_category`, `raid_reason`, `raid_outcome`, `severity`, `action_taken`, and statuses are simulated categories.

## Suggested analysis questions
1. How do raid counts vary by state, city, and month?
2. Which business types have the highest simulated violation rate?
3. What percentage of samples are non-compliant?
4. Which detected issues appear most often in non-compliant samples?
5. Which violation types are most associated with high/critical severity?
6. How do simulated enforcement actions vary by state and raid reason?
7. What is the total simulated fine amount by month, state, and action type?
8. What proportion of raids require follow-up?

## Suggested KPIs
- Total raids
- Businesses inspected
- Violations recorded
- Samples tested
- Sample non-compliance rate
- Raids requiring follow-up
- Simulated fines imposed (INR)
- High/Critical severity violations

## Suggested model
Use `food_raids` as the central fact table, joined to `food_businesses`, `food_samples`, `violations`, and `enforcement_actions`. For Power BI, be careful: joining multiple one-to-many tables directly can multiply rows and inflate totals. Prefer separate related tables or pre-aggregated measures.
