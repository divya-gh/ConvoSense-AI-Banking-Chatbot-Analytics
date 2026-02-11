🧠 Linguistic Error Types:
In conversational AI, failures usually fall into three linguistic layers:

Error Types:	                                      Question it answers
Syntax Error :                                 How is the sentence structured?
Semantics Error :	                           What does the sentence mean?
Pragmatics Error :	                           What does the user actually want in context?

### 1️⃣ Syntax Errors (Structure Problems)
What This Looks Like:
Syntax errors occur when the sentence structure confuses the model.

#### Examples:
- Long sentences with multiple clauses
- Multiple verbs joined by conjunctions
- Unusual word order

EX: “I was charged twice and want to know if I can reverse the payment”

### Analysis : 
- Tokenization showed long token sequences
- POS tagging showed multiple VERBs and conjunctions

## Business Impact: 
Syntactic Error Analysis:
Syntactic failures were observed in utterances containing multiple clauses, conjunctions, and verbs. These structures often represent compound user actions, which exceed the model’s single-intent classification design, leading to incorrect intent prediction.

### 2️⃣ Semantic Errors (Meaning Ambiguity-Multiple meaning)
#### What This Looks Like:
Semantic errors happen when words mean multiple things in banking contexts.

#### Examples:
- “charge” → fee, credit card charge, fraud
- “transfer” → internal, external, scheduled
- “payment” → bill, credit card, loan
- “Why is this charge still pending?”

### Analysis:
- Confusion matrix shows overlap between transaction-related intents
- Entity extraction is shallow or missing

## Business Imapct:
Semantic Error Analysis:
Semantic ambiguity in domain-specific terms such as "charge", "payment", and "transfer" contributed significantly to misclassification. The absence of fine-grained entity resolution limits the model’s ability to distinguish between closely related banking intents.

### 3️⃣ PragmaticErrors > Failures (Context & Expectation Mismatch)

#### Pragmatic failures occur when:
- The model predicts the correct intent
- BUT responds in a way that does not satisfy the user’s real goal

#### Example:
- User: “Why was my card declined at the gas station?”
- System: “Here’s how to check your balance.”

### Aalysis: 
✔ Intent classified correctly
❌ User goal unmet

### Our project Analyis: 
-Escalation despite correct intent
-High confidence predictions with poor resolution
-Manual review of escalated cases

## Buisness Impact:
Pragmatic Failure Analysis:
Pragmatic failures were identified in cases where the predicted intent matched the user’s query, yet the system response failed to address the user’s underlying goal. This mismatch often resulted in escalation, indicating gaps in contextual understanding and response design rather than intent classification alone.

##  Final Summary:
Linguistic Failure Taxonomy:
The analysis reveals three primary categories of conversational AI failure:

• Syntactic failures caused by complex sentence structures and multi-action requests  
• Semantic failures driven by ambiguous domain-specific terminology  
• Pragmatic failures where system responses do not align with user expectations despite correct intent classification  

Addressing these issues requires a combination of improved intent decomposition, enhanced entity modeling, and context-aware response strategies.
