---
name: discovery-brief-lite
description: Create, review, and improve discovery briefs for AISDLC (AI-Enabled Software Development Life Cycle). Discovery briefs validate problems and explore solution directions - they are NOT PRDs. Use this skill when users ask to document problem discovery, validate solution viability, or explore solution options. Discovery briefs establish "we did the research, validated the problem and viability, kicked around a few ideas and landed on one we like." Detailed requirements, user flows, designs, tech architecture, and implementation planning belong in a separate PRD document that comes AFTER the discovery brief.
license: MIT
---

# Discovery Brief Lite Skill

This skill helps you create focused discovery briefs that validate problems and explore solution directions following Diligent's AISDLC standards.

**"Lite" because:** Discovery briefs are lightweight validation documents (2-3 pages), not comprehensive PRDs.

## What is a Discovery Brief?

A discovery brief is a **lightweight validation document** that:
- Validates that a problem exists and is worth solving
- Explores potential solution directions
- Lands on a preferred approach (high-level)

**Discovery briefs are NOT PRDs.** They stop after choosing a solution direction. Detailed requirements, user flows, designs, technical architecture, and implementation planning happen in a separate PRD document.

### Workflow:
```
Discovery Brief → PRD (with designs/flows/arch) → Ticket Breakdown
```

**Discovery Brief covers:**
- Problem validation (research, evidence, personas)
- Solution exploration (what options exist?)
- Solution direction (which way are we going?)

**PRD covers** (not in this skill):
- Detailed requirements
- User flows and designs (Atlas Connector mockups)
- Technical architecture
- Dependencies and risks
- Success metrics
- Implementation planning

## When to Use This Skill

Use this skill when you need to:
- Validate a problem before investing in detailed design
- Document problem discovery research
- Explore solution options and choose a direction
- Get PM + UX alignment on problem and approach
- Create the foundation that justifies creating a PRD

**Do NOT use this skill for:**
- Detailed requirements (that's PRD)
- User flows and mockups (that's PRD)
- Technical architecture (that's PRD)
- Implementation planning (that's PRD)

## How to Use This Skill

### Prerequisites: Context and Connector Setup

**ALWAYS perform these setup steps before starting a discovery brief:**

1. **GitHub Repository Context**
   - Check if a GitHub repository is connected to the project context
   - If NO repository connected:
     - Ask: "Would you like to add a GitHub repository to the project context for this discovery brief, or is that not required?"
     - If user wants to add it, help them connect the repository
   - If repository exists, review it to understand the project scope and existing work

2. **Enable Atlassian Connector (OPTIONAL)**
   - Ask: "Would you like to search Confluence for relevant documentation or existing briefs before starting? This requires the Atlassian connector."
   - If user wants Confluence context:
     - Check if Atlassian connector is enabled
     - If NOT enabled: Instruct: "Please enable the Atlassian MCP connector in your settings."
     - Wait for confirmation before proceeding
     - Ask for Confluence space URL: "Please provide a Confluence space URL for context."
     - Use Atlassian tools to search for:
       - Existing discovery briefs or PRDs related to this feature
       - Relevant documentation about the product area
       - Previous research or user feedback
       - Team conventions or standards
   - If user doesn't want Confluence context, proceed without it

### Creating a New Discovery Brief

**ALWAYS start by reading the standard:**

```bash
file_read /mnt/skills/user/discovery-brief-lite/references/standard.md
```

When creating a discovery brief:

1. **Gather Context** - Incorporate project context and ask clarifying questions:
   - **Use project context** if available (from GitHub repo or previous work)
   - **Use Atlassian connector** to search Confluence for relevant documentation
   - Ask clarifying questions:
     - What problem are we solving?
     - Who are the target users?
     - What evidence supports this problem?
     - What's the business impact?
     - Which product/business unit?
     - What's the strategic goal?

2. **Start with the Template** - Use the Quick Start Template from the standard

3. **Build the Brief** - Follow the two-section structure:
   - **Section 1: Problem Discovery** - Validate the problem thoroughly
   - **Section 2: Solution Discovery** - Explore options and choose direction (HIGH-LEVEL only)

4. **Stop at the Right Place** - Discovery brief ends after:
   - ✅ Problem is validated
   - ✅ Solution options explored
   - ✅ Preferred solution chosen (high-level description)
   - ❌ NO detailed features, mockups, or tech specs (those go in PRD)

5. **Display and Save the Brief** - After creating the brief:
   - **ALWAYS display the discovery brief as an artifact** (using artifact tags)
   - Save the brief as a local Markdown file
   - This allows users to review the full content inline

6. **Publishing to Confluence (OPTIONAL)** - After displaying the brief:
   - Ask: "Would you like to publish this discovery brief to Confluence now?"
   - If YES:
     - Verify Atlassian connector is enabled
     - Ask for Confluence space and parent page details
     - Publish the brief to Confluence
   - If NO:
     - Inform: "The brief is ready. You can request to publish it to Confluence anytime."

### Key Principles

1. **Be Concise and Clear**
   - Discovery briefs should be relatively short (5-10 pages)
   - Focus on "why" and "what direction" not "how exactly"
   - Use simple language
   - Define acronyms on first use

2. **Problem Before Solution**
   - Spend most effort validating the problem
   - Include evidence from real users
   - Quantify the opportunity
   - Make it obvious this problem is worth solving

3. **High-Level Solution Only**
   - Describe the general approach, not detailed requirements
   - Explain which option you chose and why
   - Keep it at a conceptual level
   - Save details for the PRD

4. **No Premature Design Work**
   - Do NOT create mockups or user flows in discovery briefs
   - Do NOT detail technical architecture
   - Do NOT specify exact features and acceptance criteria
   - These belong in the PRD that comes next

### Quality Checks

Before marking a discovery brief as complete, verify:

- [ ] Discovery Status is current (DRAFT → PROBLEM DISCOVERY → SOLUTION DISCOVERY → COMPLETE)
- [ ] Problem statement is clear and specific
- [ ] Target personas identified with pain points
- [ ] Evidence provided (research, data, quotes)
- [ ] Opportunity size quantified
- [ ] Multiple solution options explored (2-3 options)
- [ ] Chosen solution direction explained (high-level)
- [ ] Rationale for chosen solution provided
- [ ] Strategic goal linked
- [ ] Sign-off table complete (PM + UX)

**Should NOT have:**
- [ ] Detailed functional requirements
- [ ] User flows or wireframes
- [ ] Technical architecture diagrams
- [ ] Implementation plans or timelines
- [ ] Detailed success metrics

### Common Brief Types

The standard covers different brief patterns:

**Feature Discovery Brief:**
- Heavy emphasis on user needs and pain points
- Include user research findings
- Focus on problem validation

**Technical/Platform Brief:**
- Emphasis on technical problem being solved
- Include performance or scalability evidence
- Focus on why current approach isn't working

**Integration Brief:**
- Emphasis on integration gaps
- Map current state limitations
- Focus on connectivity problems

**Modernization Brief:**
- Compare current vs desired state
- Include usability or technical debt evidence
- Focus on why modernization is needed

### Output Format

**Required: Display as Artifact**
- **ALWAYS display the discovery brief as an artifact** using artifact tags
- This provides an inline, reviewable document for the user
- Makes it easy to copy, edit, or share the content

**Default: Local Markdown File**
- Use Markdown format
- Include all tables and structure
- Save as a .md file that can be used locally or published later
- Keep it concise (5-10 pages typical)

**Optional: Publishing to Confluence**
- Only publish if user explicitly requests it
- Use Confluence tables for metadata
- Use proper Confluence markdown headings (# ## ###)
- Include status macros for Discovery Status
- Use @mentions for team members
- Requires Atlassian connector to be enabled

### Working with Existing Briefs

When reviewing or updating a brief:

1. Read the standard first
2. Verify brief stops at solution direction (doesn't drift into PRD territory)
3. Check that problem is thoroughly validated
4. Ensure solution options were explored
5. Confirm rationale for chosen direction is clear
6. Provide specific, actionable feedback

## Discovery Brief Structure

### Required Sections:

**Header Metadata Table:**
- Discovery Status
- Business Unit
- Product
- Assigned PM
- Strategic Goal

**Section 1: Problem Discovery**
- 1.1 Problem Statement
- 1.2 Target Users, Personas & Pain Points
- 1.3 Evidence & Insights
- 1.4 Opportunity Size

**Section 2: Solution Discovery (HIGH-LEVEL)**
- 2.1 Solution Ideas and Options (explore 2-3 alternatives)
- 2.2 Chosen Solution Direction (high-level description)
- 2.3 Rationale (why this direction?)

**Discovery Sign-offs:**
- PM Sign-off
- UX Sign-off

### What Happens Next:

After discovery brief is approved:
1. Create a PRD with detailed requirements
2. PRD includes user flows, mockups (Atlas Connector), tech architecture
3. PRD gets PM + UX + ENG sign-off
4. Then break down into tickets

## Important Notes

- **Discovery Brief ≠ PRD** - They are separate documents with different purposes
- **Keep It Light** - Discovery briefs should be quick to create (days, not weeks)
- **Problem-Focused** - Spend 70% of effort on problem validation, 30% on solution direction
- **High-Level Only** - Resist the urge to add detailed requirements
- **Sign-offs** - PM + UX only (ENG reviews PRD later)
- **Next Step** - Approved discovery brief leads to PRD creation

## Examples from Standard

The standard includes:
- Complete section-by-section requirements
- Persona table format
- Metadata table format
- Quick start template
- Quality checklist
- Common patterns by brief type

Refer to the standard for detailed examples and formats.

## Troubleshooting

**If brief is getting too detailed:**
- Stop! You're drifting into PRD territory
- Remove detailed features, flows, diagrams
- Keep solution description at high level
- Save details for PRD

**If stakeholders want more detail:**
- Explain discovery brief is for direction only
- Propose creating a PRD next
- Get discovery brief approved first

**If unsure about phase:**
- PROBLEM DISCOVERY: Defining/validating problem
- SOLUTION DISCOVERY: Exploring/choosing direction
- COMPLETE: Ready for PRD creation

**If brief seems incomplete:**
- Check it has problem validation (Section 1 complete)
- Check it has solution direction (Section 2 high-level)
- It should NOT have detailed requirements (that's PRD)
