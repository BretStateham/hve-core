---
title: RAI Impact Assessment Reviewer - Quick Start Guide
description: Quick reference guide for using the RAI Impact Assessment Reviewer chatmode agent
author: Microsoft
ms.date: 2025-12-11
ms.topic: how-to
keywords:
  - responsible ai
  - rai impact assessment
  - chatmode
  - ai ethics
  - fairness
  - safety
estimated_reading_time: 15
---

# RAI Impact Assessment Reviewer - Quick Start Guide

## Overview

The **rai-impact-assessment-reviewer** is a specialized GitHub Copilot chat mode that analyzes Microsoft Responsible AI Impact Assessment documents and provides comprehensive, actionable feedback aligned with Microsoft's RAI principles.

## When to Use This Agent

Use this agent when you need to:

* Review a completed or draft RAI Impact Assessment document
* Identify gaps in your RAI documentation
* Get specific recommendations for improving AI ethics and safety
* Evaluate compliance with Microsoft's RAI principles
* Prepare for RAI reviews or audits
* Ensure comprehensive coverage of fairness, safety, privacy, inclusiveness, transparency, and accountability

## Quick Start

### Step 1: Prepare Your Document

Ensure you have a RAI Impact Assessment document ready. It should include:

* Project information and AI system description
* Stakeholder analysis
* Risk assessments for RAI principles
* Mitigation strategies
* Monitoring and governance plans

### Step 2: Open the Agent

1. Open GitHub Copilot Chat view in VS Code (Ctrl+Alt+I or Cmd+Alt+I)
2. Click the **agent picker dropdown** at the top of the chat panel
3. Select **rai-impact-assessment-reviewer** from the list

### Step 3: Start the Review

Provide your document to the agent:

```
Review my RAI Impact Assessment at docs/rai/chatbot-assessment.md
```

Or if you have the document open:

```
Review this RAI Impact Assessment document
```

Then attach or reference the file.

### Step 4: Collaborate on Findings

The agent will guide you through a 6-phase review process:

1. **Discovery**: Confirms document location and structure
2. **Completeness Assessment**: Identifies present and missing sections
3. **Principle Analysis**: Reviews each of the 6 RAI principles systematically
4. **Risk Review**: Evaluates identified risks and mitigations
5. **Recommendations**: Provides prioritized, actionable feedback
6. **Report Generation**: Creates comprehensive review documentation

## Example Interactions

### Basic Review

```
User: Review my RAI Impact Assessment for the customer support chatbot

Agent: I'll help review your RAI Impact Assessment. Could you provide the 
       document location or attach the file?

User: It's at docs/rai/support-chatbot-assessment.md

Agent: [Reads document, creates tracking folder]
       I've analyzed your Impact Assessment for the Customer Support Chatbot.
       
       Document Structure Found:
       ✅ Project Information - Complete
       ✅ AI System Description - Complete  
       ⚠️ Risk Assessments - Partial (some TBDs found)
       ❌ Detailed Mitigations - Missing
       
       Should I proceed with the detailed principle-by-principle analysis?
```

### Quick Gap Check

```
User: What are the top 3 critical gaps in my Impact Assessment?

Agent: [Performs rapid scan]
       
       Here are the 3 most critical gaps I found:
       
       🔴 CRITICAL: Inclusiveness mitigations marked as "TBD"
          - No plan for multilingual support
          - No accessibility features defined
          - Must address before deployment
       
       🔴 CRITICAL: Privacy compliance framework missing
          - No GDPR/CCPA compliance assessment
          - Need data classification
          
       🟡 HIGH: Fairness testing procedures undefined
          - "Monitor quality" is too vague
          - Need specific metrics and test datasets
       
       Would you like me to provide detailed recommendations for any of these?
```

### Focused Review

```
User: I need help improving the fairness section of my assessment

Agent: I'll focus on the fairness analysis. Let me review that section...
       
       [Reviews fairness content]
       
       Current Fairness Assessment:
       ✅ Strength: Identified risk of historical biases
       ⚠️ Concern: Mitigation strategy is vague ("monitor quality")
       ❌ Gap: No fairness metrics defined
       ❌ Gap: No testing procedures described
       
       Specific Recommendations:
       
       1. Define Fairness Metrics
          - Identify protected attributes (age, language, etc.)
          - Define fairness metrics (e.g., demographic parity, equal opportunity)
          - Set acceptable thresholds for each metric
       
       2. Create Testing Procedures
          [detailed recommendations...]
```

## Output Files

The agent creates tracking files in `.copilot-tracking/rai-reviews/`:

* `{project-name}-review.md` - Working review notes
* `{project-name}-review-report.md` - Comprehensive final report

Example report structure:

```markdown
# Responsible AI Impact Assessment Review Report

## Executive Summary
[Overall assessment and key findings]

## Completeness Assessment
[What's present, partial, or missing]

## Principle-by-Principle Analysis
### 1. Fairness
**Status**: ⚠️ Adequate
**Strengths**: [...]
**Concerns**: [...]
**Gaps**: [...]

[Same for all 6 principles]

## Recommendations
### Critical (Must Address Before Deployment)
1. **Complete Inclusiveness Mitigations**
   - Principle: Inclusiveness
   - Issue: TBD placeholder instead of concrete plan
   - Action: Define multilingual roadmap...
   - Timeline: Before pilot launch

[Additional prioritized recommendations]

## Overall Assessment
**Readiness**: 🟡 Needs Work
**Summary**: [Overall evaluation]
**Next Steps**: [Immediate actions]
```

## The Six RAI Principles

The agent evaluates your Impact Assessment against Microsoft's six core RAI principles:

1. **Fairness**: Treating all people fairly and avoiding bias
2. **Reliability & Safety**: Performing reliably and safely under all conditions
3. **Privacy & Security**: Being secure and respecting privacy
4. **Inclusiveness**: Empowering everyone and engaging people meaningfully
5. **Transparency**: Being understandable and explainable
6. **Accountability**: Having clear accountability for AI systems and impacts

## Best Practices

### Before Review

* Complete as much of your Impact Assessment as possible
* Gather supporting documentation (architecture diagrams, data inventories, etc.)
* Identify known gaps or areas of concern
* Have stakeholder information ready

### During Review

* Engage actively with the agent's questions
* Provide context when asked
* Be honest about uncertainties or TBDs
* Ask for clarification on recommendations you don't understand

### After Review

* Prioritize critical issues identified
* Create action items from recommendations
* Set timelines for addressing gaps
* Plan for follow-up review after improvements

## Common Scenarios

### Scenario 1: Pre-Deployment Review

**Goal**: Ensure readiness before launching AI system

**Approach**:
1. Complete full Impact Assessment
2. Use agent for comprehensive review
3. Address all critical and high-priority items
4. Schedule follow-up review
5. Obtain necessary approvals

### Scenario 2: Iterative Improvement

**Goal**: Improve existing Impact Assessment over time

**Approach**:
1. Start with partial assessment
2. Get initial feedback
3. Address one principle at a time
4. Re-review improved sections
5. Build completeness incrementally

### Scenario 3: Specific Principle Focus

**Goal**: Deep dive on one RAI principle

**Approach**:
1. Request focused review on specific principle
2. Get detailed recommendations
3. Implement improvements
4. Request re-review of that section
5. Move to next principle

## Tips for Success

* **Be Specific**: The more context you provide, the better the feedback
* **Iterate**: Don't expect perfection on first draft - RAI is iterative
* **Ask Questions**: If recommendations aren't clear, ask for clarification
* **Prioritize**: Focus on critical issues first
* **Document**: Keep review reports for compliance and audit trails
* **Follow Up**: Re-review after making significant improvements

## Integration with Development Workflow

### Early Stage (Design)

* Create initial Impact Assessment
* Get early feedback on approach
* Identify potential issues before development

### Mid Stage (Development)

* Update assessment with implementation details
* Re-review with actual architecture and data
* Adjust mitigations based on technical constraints

### Pre-Launch (Testing)

* Final comprehensive review
* Address any remaining critical gaps
* Document readiness decision

### Post-Launch (Operations)

* Periodic re-review with operational data
* Update based on actual performance
* Adjust mitigations as needed

## Resources

* [Microsoft Responsible AI](https://www.microsoft.com/ai/responsible-ai)
* [Microsoft Responsible AI Standard](https://www.microsoft.com/ai/responsible-ai-resources)
* [RAI Impact Assessment Template](https://www.microsoft.com/ai/responsible-ai-impact-assessment)
* [Azure Responsible AI Resources](https://learn.microsoft.com/azure/machine-learning/concept-responsible-ai)

## Troubleshooting

**Agent not finding document:**
* Verify file path is correct
* Try providing absolute path
* Ensure file is in workspace

**Review seems incomplete:**
* Ensure document has required sections
* Provide additional context when asked
* Try breaking review into focused sessions

**Recommendations not specific enough:**
* Provide more detail about your AI system
* Share technical architecture or data details
* Ask for clarification on specific recommendations

## Getting Help

* Ask the agent for clarification on any recommendations
* Request examples of strong RAI Impact Assessment content
* Seek guidance on specific RAI principles
* Consult Microsoft RAI resources for detailed frameworks

---

*This guide is maintained by the HVE Core team. Last updated: December 2025*
