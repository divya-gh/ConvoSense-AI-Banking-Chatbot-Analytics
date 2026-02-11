# Fallback & Clarification Strategy

## 1️⃣ Purpose

Handles cases where:
- Intent confidence is low
- User input is ambiguous
- The system fails to understand user request
- Conversation context is incomplete

## Examples from our project:

### Lynguistic Analysis : 

## 2️⃣ Types of Failures : Failure Categories Observed
1. Syntactic Errors
   - Typos
   - Fragmented sentences
   - Grammar issues

2. Semantic Errors
   - Intent misclassification
   - Entity extraction failures

3. Pragmatic Failures
   - System response does not match user intent
   - Context misunderstanding

## 3️⃣ Clarification Strategy
#### Level 1: Rephrase Request
"Just to confirm, are you asking about a duplicate charge?"

#### Level 2: Offer Options
"Are you trying to:
1. Dispute a charge
2. Check a transaction
3. Report fraud?"

#### Level 3: Escalation
After 2 failed attempts → Route to Agent Escalation Flow.

## 4️⃣ Confidence-Based Routing
#### If intent confidence < 0.75:
→ Route to Fallback Flow

#### If repeated fallback occurs:
→ Escalate to human agent

## 5️⃣ Example
#### User: "money gone twice idk why"

System:
Step 1: Detect low confidence
Step 2: Ask clarification
"Are you referring to a duplicate charge on your account?"

If confirmed → Route to Charge Dispute subflow.
