# Home Credit LAP Pre-Qualification AI Voice Agent

An AI-powered voice agent built using **Retell AI** to conduct preliminary eligibility screening for a Loan Against Property (LAP). The agent guides customers through a structured conversation, collects required information, identifies disqualifying conditions, and routes eligible cases or existing property-loan requests to the appropriate next step.

## Overview

The goal of this project is to automate the initial customer qualification process through a conversational voice interface.

The agent asks relevant questions, understands answers provided in different orders, handles interruptions and corrections, and determines whether the customer can proceed to a senior loan expert for further discussion.

**Important:** This project performs preliminary qualification only. It does not approve loans, calculate final offers, or guarantee loan eligibility.

## Features

- **Conversational voice interaction:** Communicates with customers using a professional and customer-friendly tone.
- **Structured eligibility screening:** Collects the information required for preliminary LAP qualification.
- **Property type validation:** Accepts residential, commercial, and industrial properties; agricultural property is disqualified.
- **Ownership verification:** Supports sole and joint property ownership.
- **Document availability check:** Verifies that original property documents are available.
- **Loan amount validation:** Supports requests up to ₹75,00,000 and offers the customer the option to proceed with the maximum amount when they request more.
- **Income verification:** Accepts salaried and self-employed customers whose income is received through a bank; cash income is disqualified.
- **Tenure validation:** Accepts requested tenures from 3 to 15 years, inclusive.
- **Existing loan routing:** Directs existing property-loan transfer and EMI-reduction requests to a specialist pathway.
- **Interruption handling:** Handles customers who are busy, ask questions, or provide information out of order.
- **Answer correction handling:** Reassesses eligibility when a customer clearly corrects an earlier answer.
- **Responsible qualification:** Does not promise final loan approval or invent interest rates, fees, or other loan terms.

## Technology Stack

- **Retell AI** — Voice agent configuration and conversational interaction.
- **LLM-powered conversation handling** — Interprets customer responses and follows the qualification instructions configured in the agent prompt.

The project is configured as a Retell AI voice agent. Additional integrations, databases, or backend services should only be listed here if they have actually been implemented.

## Customer Qualification Workflow

1. **Greeting and identity verification**  
   The agent confirms that it is speaking with the intended customer before discussing the offer.

2. **Availability check**  
   If the customer is busy, the agent asks for a preferred callback time and ends the conversation without proceeding with the pitch.

3. **Offer introduction**  
   The agent introduces the preliminary Loan Against Property offer of up to ₹75 lakh.

4. **Existing property-loan check**  
   If the customer wants to transfer an existing property loan or reduce an EMI, the agent directs the request to a specialist.

5. **Eligibility information collection**  
   The agent gathers the seven required checklist items.

6. **Eligibility evaluation**  
   The agent evaluates the answers against the configured qualification rules.

7. **Final routing**
   - **Potentially eligible:** Refers the customer to a senior loan expert for the next steps.
   - **Not eligible:** Politely explains the relevant disqualifying condition and ends the qualification flow.
   - **Existing property-loan request:** Routes the customer to the specialist pathway.
   - **Busy customer:** Captures the preferred callback time and ends the call.

## Eligibility Checklist

| Checklist item | Qualification rule |
|---|---|
| Property type | Residential, commercial, or industrial |
| Ownership | Sole or joint ownership |
| Original documents | Original property documents must be available |
| Loan amount | Up to ₹75,00,000 |
| Occupation and income mode | Salaried or self-employed; income must be received through a bank |
| Property market value | Captured for preliminary assessment; no unsupported minimum threshold is imposed |
| Loan tenure | Between 3 and 15 years, inclusive |

### Special Rules

- Agricultural property does not qualify.
- If the customer requests more than ₹75 lakh, the agent explains the cap and asks whether the customer is willing to proceed with ₹75 lakh.
- If the customer declines the capped amount, the qualification flow ends politely.
- If the customer clearly corrects an earlier answer, the agent updates the answer and reassesses eligibility.
- A corrected answer does not override other disqualifying conditions.
- The agent does not invent loan rates, fees, or approval conditions.

## Testing and Validation

The agent was tested against the following scenarios:

| Test case | Scenario | Expected behavior |
|---|---|---|
| TC01 | Eligible customer | Collect all required details and refer for further assessment |
| TC02 | Agricultural property | Explain the eligibility restriction and end the flow |
| TC03 | Cash income | Disqualify the customer |
| TC04 | Existing property loan | Route the request to a specialist pathway |
| TC05 | Loan amount above ₹75 lakh | Offer the ₹75 lakh cap and continue only if accepted |
| TC06 | Busy customer | Ask for a preferred callback time and end the call |
| TC07 | Out-of-order answers | Extract provided information and ask only for missing or unclear details |

Additional recommended tests include missing original documents, tenure boundary values, ambiguous answers, requests for interest rates, and corrections to previously disqualifying answers.

## Prompt Design and Conversation Management

The agent uses a structured system prompt to define:

- Its role and objective.
- Greeting and identity-verification behavior.
- Offer wording and qualification sequence.
- Eligibility and disqualification rules.
- Existing property-loan routing.
- State tracking and avoidance of repeated questions.
- Handling of interruptions, ambiguous responses, and corrections.
- Appropriate closing statements and limitations.

The prompt is designed to keep qualification decisions consistent while allowing customers to answer questions naturally.

## Limitations

- Qualification is preliminary and does not constitute loan approval.
- Actual interest rates, fees, final eligibility, and loan terms require confirmation by an authorized loan expert.
- Callback preferences and referrals are recorded conversationally; they should not be considered scheduled or completed unless a connected system confirms the action.
- The project should not be used for real customer outreach or presented as an officially authorized Home Credit service without the appropriate authorization and integrations.

## Demo and Project Links

- **Published voice agent / demo:** https://agent.retellai.com/orb/agent_b436b0bd73525cb7e6867f0a97?token=32f6d35eb1c12726d259efd136199352
- **GitHub repository:** https://github.com/RahulK512005/AI-Voice-Agent-By-retellai.git
- **Screen recording:** https://drive.google.com/file/d/11iYmXw7p22GqUGNTRwCLO10YiFS4by0y/view?usp=sharing

## Future Improvements

- Integrate a CRM to securely store customer qualification details.
- Connect an authorized callback scheduling system.
- Add a secure handoff mechanism for senior loan experts and specialists.
- Generate structured call summaries and qualification outcomes.
- Add automated regression tests for eligibility rules and customer corrections.
- Improve multilingual support and speech recognition for different accents.

## Conclusion

The Home Credit LAP Pre-Qualification AI Voice Agent demonstrates how conversational AI can support an initial loan qualification workflow. By combining structured screening rules with natural voice interaction, the project aims to make preliminary customer assessment more consistent and efficient while keeping final lending decisions with authorized professionals.
