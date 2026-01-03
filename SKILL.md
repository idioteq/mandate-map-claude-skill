---
name: investment-mandate
description: Access and validate against the Shariah Global Equity Strategy investment mandate. Use when user asks about investment guidelines, mandate constraints, portfolio rules, compliance requirements, Shariah screening, position limits, or UCITS constraints.
allowed-tools: Read, Grep, Bash
---

# Investment Mandate Reference Skill

Provides quick access to the Shariah Global Equity Strategy investment mandate and helps validate portfolio decisions against mandate constraints.

## What This Skill Does

This skill provides:
1. **Quick reference** to investment mandate constraints and rules
2. **Validation** of portfolio decisions against mandate requirements
3. **Compliance checking** for proposed trades or positions
4. **Mandate interpretation** for specific investment scenarios

## When to Use This Skill

Use this skill when the user:
- Asks about "investment guidelines", "mandate", "investment rules", or "portfolio constraints"
- Wants to check if a trade or position is "allowed" or "compliant"
- Asks about position limits, sector limits, country limits, or concentration rules
- Questions about Shariah screening criteria or compliance
- Needs to verify UCITS constraints
- Asks about leverage, derivatives, or borrowing rules
- Questions about rebalancing triggers or trading guidelines

## Mandate Document Location

The current investment mandate is located at:
`/Users/jeremy/Invest/Investment guidelines/Investment_Mandate_Shariah_Global_Equity_Strategy_CURRENT.md`

## Key Mandate Constraints (Quick Reference)

### Portfolio Structure
- **Holdings:** 20-40 stocks (target: 25-35)
- **Benchmark:** MSCI World Islamic Index
- **Target Outperformance:** +3% per annum
- **Time Horizon:** Long-term (5+ years)

### Position Limits
- **Max single stock:** 8% of NAV
- **Max active position:** +5% vs benchmark
- **Min position size:** 1% of NAV
- **Top 10 holdings:** Max 45% of NAV

### Sector Limits
- **Max sector overweight:** +8% vs benchmark
- **Max sector underweight:** -8% vs benchmark
- **Max absolute sector:** 35% of NAV

### Country Limits
- **Max country overweight:** +10% vs benchmark
- **Max country underweight:** -10% vs benchmark
- **Max single country:** 40% of NAV
- **Emerging markets:** Max 20% of NAV

### Risk Constraints
- **Target Tracking Error:** 6% per annum
- **Tracking Error Range:** 4-8% per annum
- **Max Tracking Error:** 12% per annum
- **Beta Range:** 0.75 - 1.25 (vs benchmark, 36-month rolling)

### Shariah Compliance
- **Business Activity Screens:** Exclude companies with >5% revenue from alcohol, tobacco, gambling, pork, conventional finance, weapons, adult entertainment
- **Financial Ratios:**
  - Total debt / Total assets < 33%
  - Interest-bearing securities / Total assets < 33%
  - Accounts receivable / Total assets < 49%
  - Impure income / Total revenue < 5%

### UCITS Constraints
- **5/10/40 Rule:** Max 10% in single issuer, max 40% aggregate in issuers >5%
- **Liquidity:** Min 80% liquidable within 7 days
- **Derivatives:** Max 10% of NAV (hedging only)

### Leverage & Derivatives
- **Leverage:** NOT permitted
- **Cash Borrowing:** Max 10% of NAV (30 days max, Shariah-compliant only)
- **Permitted Derivatives:** Currency forwards, index futures, single stock futures (hedging/EPM only)
- **Prohibited:** Options, swaps, CFDs, structured products

## Instructions

### Step 1: Identify User Query Type

Determine what the user is asking about:
1. **Specific constraint lookup:** "What's the max position size?"
2. **Compliance validation:** "Can I buy 10% of this stock?"
3. **Portfolio review:** "Does my portfolio comply with the mandate?"
4. **Shariah screening:** "Is this company Shariah-compliant?"
5. **General mandate reference:** "Show me the investment guidelines"

### Step 2: Access Mandate Document

Read the relevant sections from:
`/Users/jeremy/Invest/Investment guidelines/Investment_Mandate_Shariah_Global_Equity_Strategy_CURRENT.md`

Use targeted reading:
- For position limits → Section 7 (Portfolio Construction Rules)
- For Shariah screening → Section 3 (Investment Universe)
- For risk constraints → Section 6 (Risk Constraints)
- For UCITS rules → Section 10 (UCITS Compliance)
- For derivatives → Section 9 (Use of Derivatives)

### Step 3: Provide Clear Answer

**For constraint lookups:**
- Quote the specific rule from the mandate
- Provide the section reference
- Include any relevant context or exceptions

**For compliance validation:**
- State whether the proposed action complies (YES/NO)
- Reference the specific constraint
- If non-compliant, explain why and suggest alternatives
- If compliant, confirm and provide headroom (e.g., "Within limit, 3% headroom remaining")

**For portfolio reviews:**
- Check against all relevant constraints
- Highlight any breaches or near-breaches
- Provide actionable remediation steps if needed

### Step 4: Proactive Guidance

When answering, also mention:
- Related constraints the user should be aware of
- Common gotchas or edge cases
- Best practices for staying well within limits
- Monitoring or reporting requirements

## Example Usage

**User:** "What's the maximum I can invest in a single stock?"

**Claude:**
Reading the investment mandate...

According to Section 7 (Portfolio Construction Rules):
- **Maximum single stock weight:** 8% of portfolio NAV
- **Maximum active position:** +5% vs benchmark weight
- **Minimum position size:** 1% of NAV

This means:
- Absolute maximum: 8% of your portfolio
- If the stock is in the benchmark, you can hold up to 8%
- If the stock is outside the benchmark, the limit is lower (5% absolute per Section 7)
- Any position must be at least 1% to be meaningful

Also note: The top 10 holdings combined cannot exceed 45% of NAV.

**User:** "Can I hold 12% in Microsoft?"

**Claude:**
❌ **NO** - This would breach the mandate.

According to Section 7:
- Maximum single stock weight: 8% of NAV
- 12% would exceed this limit by 4%

**Recommendation:**
- Reduce MSFT position to 8% or below
- Consider the max active position rule (+5% vs benchmark)
- If MSFT is 4% in benchmark, you could hold max 9% (4% + 5%), but the absolute 8% limit still applies

**User:** "Show me the Shariah screening criteria"

**Claude:**
Reading Section 3 (Investment Universe)...

[Provides detailed Shariah screening criteria from the mandate]

## Important Notes

- Always reference the **CURRENT** version of the mandate document
- Version shown in document: Check the Document Control section for latest version
- When in doubt about interpretation, suggest consulting with investment committee
- For Shariah-specific questions beyond basic screening, note that Shariah advisory board oversight may be required
- Mandate is reviewed annually - check review date

## Validation Workflow

For portfolio compliance checks:
1. Read current portfolio positions (if user provides file)
2. Read mandate constraints
3. Check each constraint systematically:
   - Position sizes (individual and top 10)
   - Sector exposures
   - Country exposures
   - UCITS 5/10/40 rule
   - Liquidity requirements
   - Derivatives exposure
   - Shariah compliance status
4. Report findings with clear PASS/FAIL/WARNING status
5. Provide remediation steps for any breaches

## Error Handling

If mandate document is not found or outdated:
- Check alternative location: `/Users/jeremy/Invest/Investment guidelines/`
- Look for latest version file
- Inform user if document appears outdated (check version date)

## Integration with Other Skills

This skill works well with:
- **portfolio-risk-report:** For validating risk constraints (TE, beta, volatility)
- Portfolio construction tools: For validating proposed portfolios before trading
- Trade validation: For checking individual trades against mandate

---

**Skill Version:** 1.0
**Mandate Version Supported:** 1.2
**Last Updated:** 2025-01-02
