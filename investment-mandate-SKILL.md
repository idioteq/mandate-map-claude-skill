# Investment Mandate Document Creation Skill

## Purpose
Create comprehensive, institutionally-formatted investment mandate documents for equity portfolios. Generates structured markdown documents covering all key governance and compliance requirements for institutional asset management.

## When to Use
Use this skill when users request:
- "Create an investment mandate"
- "Draft a mandate document"
- "Write up investment guidelines"
- "Generate mandate documentation"
- Any request to formalize portfolio investment rules and constraints

## Output Format
Always create a markdown (.md) file saved to `/mnt/user-data/outputs/` with filename pattern: `Investment_Mandate_[Portfolio_Name]_[Date].md`

## Document Structure

### Required Sections

1. **Mandate Overview**
   - Mandate name
   - Client/fund name
   - Effective date
   - Review date
   - Version number

2. **Investment Objective**
   - Clear statement of primary objective (capital appreciation, income, total return)
   - Time horizon
   - Target investor profile

3. **Investment Universe**
   - Geographic scope (global, regional, single country)
   - Market cap range
   - Sector inclusions/exclusions
   - Liquidity requirements
   - Any specific security type restrictions

4. **Benchmark**
   - Primary benchmark index
   - Rationale for benchmark selection
   - Benchmark currency
   - Rebalancing frequency of benchmark

5. **Performance Targets**
   - Absolute return target (if applicable)
   - Relative return target vs benchmark (e.g., +2% p.a. over rolling 3 years)
   - Measurement period
   - Risk-adjusted performance metrics (Sharpe ratio, information ratio targets if applicable)

6. **Risk Constraints**
   - **Active Risk (Tracking Error)**
     - Ex-ante tracking error limit (e.g., 3-6% p.a.)
     - Ex-post tracking error monitoring
   - **Volatility constraints** (if absolute)
   - **Maximum drawdown limits** (if applicable)
   - **Beta constraints** (if applicable)

7. **Portfolio Construction Rules**
   - **Number of holdings**: Minimum and maximum number of stocks
   - **Position sizing**: 
     - Maximum single stock weight (absolute and relative to benchmark)
     - Minimum position size (if applicable)
   - **Concentration Limits**:
     - Sector: Maximum overweight/underweight vs benchmark
     - Country: Maximum exposure limits
     - Top 10 holdings: Maximum aggregate weight
     - Single issuer limits
   
8. **Leverage and Borrowing**
   - Permitted leverage (typically "No leverage permitted" or specific limit)
   - Cash borrowing limits (if any)
   - Synthetic leverage through derivatives

9. **Use of Derivatives**
   - Permitted derivative types (futures, options, swaps, forwards)
   - Purpose (hedging only, efficient portfolio management, or investment)
   - Counterparty risk limits
   - Collateral requirements
   - Gross/net notional limits

10. **UCITS Compliance** (if applicable)
    - Confirm UCITS eligibility
    - 5/10/40 rule compliance (5% single issuer limit, 10% aggregate for issuers >5%, 40% maximum in issuers representing >5%)
    - Eligible markets requirement
    - Derivative exposure limits (VaR or commitment approach)
    - Risk management process reference

11. **Liquidity Requirements**
    - Minimum average daily trading volume for holdings
    - Maximum illiquid holdings percentage
    - Redemption timeline considerations

12. **ESG/Sustainability Criteria** (if applicable)
    - Exclusion lists
    - ESG integration approach
    - Sustainability disclosures (SFDR Article 6/8/9 if EU-relevant)

13. **Rebalancing and Trading**
    - Rebalancing frequency and triggers
    - Transaction cost budget
    - Best execution policy reference

14. **Reporting Requirements**
    - Performance reporting frequency
    - Risk reporting frequency
    - Attribution analysis
    - Compliance monitoring reports

15. **Governance**
    - Investment committee oversight
    - Breach notification procedures
    - Mandate review frequency
    - Amendment process

## Best Practices

### Tone and Language
- Professional, precise, and unambiguous
- Use standard institutional investment terminology
- Avoid jargon where plain language suffices
- Be specific with numbers (use ranges where appropriate: "4-6% tracking error" rather than "moderate tracking error")

### Formatting Guidelines
- Use clear hierarchical headers (##, ###)
- Present limits in table format where helpful
- Include specific numeric constraints, not vague terms
- Use bullet points for lists of criteria
- Bold key constraint figures for easy reference

### Information Gathering
Before generating the document, gather from the user:
1. Basic mandate details (name, client, strategy type)
2. Geographic/sector focus
3. Benchmark
4. Key constraints (tracking error, number of stocks, leverage)
5. UCITS requirement (yes/no)
6. Any specific client requirements or restrictions

If critical information is missing, ASK before generating. Don't assume - mandates are legal documents.

### Common Patterns by Strategy Type

**Long-only focused equity:**
- Typical tracking error: 2-6%
- Number of stocks: 30-80
- Max single stock: 5-10% absolute, +3-5% vs benchmark
- No leverage
- Derivatives for hedging/EPM only

**Long-only high conviction:**
- Typical tracking error: 6-12%
- Number of stocks: 20-40
- Max single stock: 8-15% absolute
- Potentially higher concentration limits

**UCITS-compliant:**
- Must include 5/10/40 rule
- Maximum 10% in single issuer (with specific exemptions)
- Liquid transferable securities only
- Specific derivative exposure limits

## Example Interaction

**User:** "Create a mandate for a European equity fund"

**Claude response:**
"I'll help you create a European equity investment mandate. Let me gather some key details:

1. What's the fund/mandate name?
2. What's the benchmark? (e.g., MSCI Europe, STOXX Europe 600)
3. What's the active risk budget? (typical range: 2-6% tracking error)
4. How many stocks do you expect to hold? (range is fine, e.g., 40-70)
5. Does this need to be UCITS compliant?
6. Any leverage permitted, or long-only unleveraged?
7. Can derivatives be used for investment purposes, or only hedging?
8. Are there any specific ESG exclusions or requirements?
9. What's the performance target vs benchmark?"

[After receiving answers, generate complete mandate document]

## Quality Checks

Before finalizing:
- ✓ All numeric limits are clearly specified
- ✓ UCITS requirements fully detailed if applicable
- ✓ Benchmark clearly identified
- ✓ Concentration limits are mathematically consistent
- ✓ Derivative usage clearly bounded
- ✓ Performance measurement period specified
- ✓ Review/approval process included

## Notes

- Investment mandates are governance documents - precision matters
- When in doubt about institutional standards, ask the user
- Different clients may have house styles - be flexible
- Always include version number and effective date
- This creates the mandate document; it doesn't provide investment advice on what the constraints should be
