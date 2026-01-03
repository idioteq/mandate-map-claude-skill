# Investment Mandate Skills for Claude

Two complementary Claude skills for managing investment mandates: one for creating new mandate documents, and one for referencing and validating against existing mandates.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Skills Included](#skills-included)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [File Structure](#file-structure)
- [Requirements](#requirements)

---

## 🎯 Overview

These skills help portfolio managers and investment professionals work with investment mandate documents in Claude:

1. **Mandate Creator** - Generate comprehensive, institutionally-formatted investment mandate documents
2. **Mandate Reference** - Query and validate portfolio decisions against existing mandate constraints

---

## 📦 Skills Included

### 1. Mandate Creator (`investment-mandate-SKILL.md`)

**Purpose:** Create new investment mandate documents from scratch

**When to use:**
- Starting a new fund or portfolio strategy
- Formalizing investment guidelines for clients
- Documenting portfolio rules and constraints
- Generating UCITS-compliant mandate documentation

**What it does:**
- Guides you through mandate creation with structured questions
- Generates professionally-formatted markdown documents
- Includes all institutional sections (objectives, constraints, governance, etc.)
- Ensures UCITS compliance (if required)
- Outputs to: `/mnt/user-data/outputs/`

**Trigger phrases:**
- "Create an investment mandate"
- "Draft mandate documentation"
- "Generate investment guidelines"

---

### 2. Mandate Reference (`SKILL.md`)

**Purpose:** Reference and validate against an existing investment mandate

**When to use:**
- Checking if a trade complies with mandate rules
- Looking up specific constraints (position limits, sector limits, etc.)
- Validating portfolio against mandate requirements
- Ensuring Shariah compliance
- Verifying UCITS constraints

**What it does:**
- Reads your existing mandate document
- Answers questions about constraints and limits
- Validates proposed trades and positions
- Checks portfolio compliance
- Provides clear PASS/FAIL validation

**Trigger phrases:**
- "What's the maximum position size?"
- "Can I hold 10% in Apple?"
- "Show me the Shariah screening criteria"
- "Does my portfolio comply with the mandate?"

**Configured for:**
- Mandate location: `/Users/jeremy/Invest/Investment guidelines/Investment_Mandate_Shariah_Global_Equity_Strategy_CURRENT.md`
- Can be customized to point to your mandate location

---

## 🚀 Installation

### Step 1: Locate Your Claude Skills Directory

The skills directory is typically located at:
```
~/.claude/skills/
```

On Mac/Linux:
```bash
cd ~/.claude/skills/
```

On Windows:
```powershell
cd %USERPROFILE%\.claude\skills\
```

### Step 2: Create the Skill Directory

```bash
mkdir -p ~/.claude/skills/investment-mandate
cd ~/.claude/skills/investment-mandate
```

### Step 3: Add the Skill Files

Copy or clone these files into the directory:

```
~/.claude/skills/investment-mandate/
├── SKILL.md                          # Mandate Reference skill
├── investment-mandate-SKILL.md       # Mandate Creator skill
└── README.md                         # This file
```

**From GitHub:**
```bash
cd ~/.claude/skills/
git clone https://github.com/YOUR-USERNAME/investment-mandate-skills.git investment-mandate
```

**Or manually:**
- Download the `.md` files
- Place them in `~/.claude/skills/investment-mandate/`

### Step 4: Verify Installation

1. Restart Claude (if using CLI) or refresh your session
2. Ask: "What skills do I have installed?"
3. You should see `investment-mandate` listed

---

## 💡 Usage

### Using the Mandate Creator

**Example workflow:**

```
You: Create an investment mandate for a European equity fund

Claude: I'll help you create a European equity investment mandate.
Let me gather some key details:

1. What's the fund/mandate name?
2. What's the benchmark? (e.g., MSCI Europe)
3. What's the tracking error budget? (e.g., 4-6%)
...

[Claude generates complete mandate document]
```

**Output:**
- File created in `/mnt/user-data/outputs/`
- Filename: `Investment_Mandate_[Portfolio_Name]_[Date].md`
- Professionally formatted with all required sections

---

### Using the Mandate Reference

**Example queries:**

**1. Check position limits:**
```
You: What's the maximum I can invest in a single stock?

Claude: According to Section 7 (Portfolio Construction Rules):
- Maximum single stock weight: 8% of portfolio NAV
- Maximum active position: +5% vs benchmark weight
- Minimum position size: 1% of NAV
```

**2. Validate a trade:**
```
You: Can I hold 10% in Microsoft?

Claude: ❌ NO - This would breach the mandate.

According to Section 7:
- Maximum single stock weight: 8% of NAV
- 10% would exceed this limit by 2%

Recommendation:
- Reduce MSFT position to 8% or below
```

**3. Look up constraints:**
```
You: What are the sector limits?

Claude: According to Section 7 (Portfolio Construction Rules):
- Maximum sector overweight: +8% vs benchmark
- Maximum sector underweight: -8% vs benchmark
- Maximum absolute sector exposure: 35% of portfolio NAV
```

**4. Check Shariah compliance:**
```
You: Show me the Shariah screening criteria

Claude: [Provides detailed Shariah business activity screens and financial ratios]
```

**5. Portfolio compliance check:**
```
You: Check if my portfolio complies with the mandate

Claude: [Systematic validation of all constraints with PASS/FAIL status]
```

---

## 📁 File Structure

```
~/.claude/skills/investment-mandate/
│
├── SKILL.md                          # Main skill file for mandate reference
│   ├── Skill metadata (name, description, allowed-tools)
│   ├── Quick reference constraints
│   ├── Usage instructions
│   └── Validation workflows
│
├── investment-mandate-SKILL.md       # Skill file for mandate creation
│   ├── Document structure templates
│   ├── Best practices and guidelines
│   ├── Information gathering workflows
│   └── Quality check criteria
│
└── README.md                         # This documentation file
```

---

## 📋 Requirements

### For Mandate Reference Skill:

1. **Existing mandate document** in markdown format
2. Update the mandate location in `SKILL.md` (line ~31):
   ```markdown
   `/Users/jeremy/Invest/Investment guidelines/Investment_Mandate_Shariah_Global_Equity_Strategy_CURRENT.md`
   ```
   Change this path to your mandate location.

3. **Allowed tools:** Read, Grep, Bash
   - These are specified in the skill metadata and allow Claude to read your mandate file

### For Mandate Creator Skill:

1. **Output directory:** `/mnt/user-data/outputs/`
   - Ensure this directory exists or update the path in the skill file

2. **No external dependencies** - generates markdown files directly

---

## 🔧 Customization

### Point to Your Own Mandate

Edit `SKILL.md` and update the path:

```markdown
## Mandate Document Location

The current investment mandate is located at:
`/path/to/your/mandate/Investment_Mandate.md`
```

### Modify Quick Reference Constraints

In `SKILL.md`, section "Key Mandate Constraints (Quick Reference)", update the values to match your mandate:

```markdown
### Position Limits
- **Max single stock:** 8% of NAV  ← Update this
- **Max active position:** +5% vs benchmark  ← Update this
```

### Change Skill Names

To avoid conflicts, you can rename the skills by editing the metadata:

In `SKILL.md`:
```yaml
---
name: my-mandate-reference  ← Change this
description: Your description
---
```

---

## 🎓 Best Practices

### When Creating Mandates:
✅ Gather all requirements before generating
✅ Be specific with numeric constraints
✅ Use standard institutional terminology
✅ Include version control and review dates
✅ Document all assumptions clearly

### When Using Mandate Reference:
✅ Always check against the latest mandate version
✅ Validate trades BEFORE execution
✅ Review portfolio compliance regularly
✅ Document any breaches and remediation plans
✅ Keep mandate document up-to-date

---

## 📝 Example Mandate Sections

The Mandate Creator generates documents with these sections:

1. Mandate Overview
2. Investment Objective
3. Investment Universe (including Shariah screening if applicable)
4. Benchmark
5. Performance Targets
6. Risk Constraints
7. Portfolio Construction Rules
8. Leverage and Borrowing
9. Use of Derivatives
10. UCITS Compliance (if applicable)
11. Liquidity Requirements
12. ESG/Sustainability Criteria
13. Rebalancing and Trading
14. Reporting Requirements
15. Governance

---

## 🤝 Integration with Other Skills

These skills work well with:

- **portfolio-risk-report:** Validate risk constraints (tracking error, beta, volatility)
- **Portfolio construction tools:** Check proposed portfolios before trading
- **Trade execution systems:** Pre-trade compliance validation

---

## 📄 License

[Specify your license here]

---

## 👤 Author

[Your name/organization]

---

## 🐛 Issues and Contributions

If you find issues or have suggestions:
1. Open an issue on GitHub
2. Submit a pull request with improvements
3. Share your use cases and feedback

---

## ⚠️ Disclaimer

These skills are tools to help manage investment mandates. They do not constitute investment advice. Always:
- Verify all constraint interpretations with legal/compliance teams
- Consult Shariah advisors for religious compliance matters
- Follow your organization's governance procedures
- Maintain proper documentation and audit trails

Investment mandates are legal governance documents - use these skills as aids, not replacements for professional oversight.

---

## 📚 Additional Resources

- [Claude Skills Documentation](https://docs.anthropic.com/claude/docs)
- UCITS Directive and Regulations
- MSCI Islamic Index Methodology
- Your firm's investment policy documentation

---

**Version:** 1.0
**Last Updated:** 2025-01-03
**Compatible with:** Claude 3.5 Sonnet and later
