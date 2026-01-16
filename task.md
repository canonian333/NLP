# 📚 Regex & NLP Practice Exercises

## 🟢 Level 1: BEGINNER REGEX EXERCISES

### Exercise 1.1: Date Extraction
- Extract dates in various formats: `DD/MM/YYYY`, `MM-DD-YYYY`, `YYYY-MM-DD`
- Bonus: Extract relative dates like "yesterday", "last week", "two days ago"
- **Expected Output**: List of all date mentions per chat

### Exercise 1.2: Urgency Detection
- Find messages containing "urgent", "ASAP", "immediately", "priority"
- Make it case-insensitive
- Count urgency indicators per chat
- **Expected Output**: Boolean flag + urgency score (0-5)

### Exercise 1.3: Postal Code Extraction
- Extract Indian PIN codes: 6 digits (e.g., 560001)
- Extract US ZIP codes: 5 digits or 5+4 format (e.g., 12345, 12345-6789)
- Extract UK postcodes: Alphanumeric format (e.g., SW1A 1AA)
- **Expected Output**: Column with postal codes + country detected

### Exercise 1.4: Acronym Finder
- Find 2-4 letter capital acronyms (AC, ID, PIN, OTP)
- Exclude single letters and common words (A, I, IT)
- **Expected Output**: List of unique acronyms per chat

### Exercise 1.5: Time Extraction
- Extract time mentions: "10:30 AM", "14:00", "2 PM"
- Extract time ranges: "9 AM to 5 PM"
- **Expected Output**: Structured time data

---

## 🟡 Level 2: INTERMEDIATE REGEX EXERCISES

### Exercise 2.1: Multi-Format ID Extraction
Create patterns for these ID types:
- Transaction IDs: `TXN-123456-AB`, `TX123456`
- Invoice IDs: `INV-2024-001234`, `#INV123`
- Reference IDs: `REF-XXXXXX-X`
- **Expected Output**: Separate columns for each ID type with format validation

### Exercise 2.2: Phone Number Segmentation
Build separate patterns for:
- Indian mobile: `+91-XXXXX-XXXXX`, `98XXXXXXXX`
- Indian landline: `080-XXXX-XXXX`, `(080) XXXXXXXX`
- US numbers: `+1-XXX-XXX-XXXX`, `(XXX) XXX-XXXX`
- International format: `+XX-XXXX-XXXX`
- **Expected Output**: Phone type classification + country code extraction

### Exercise 2.3: Currency & Amount Extraction
- Extract amounts with currency symbols: `$100`, `₹500`, `€50`
- Extract written amounts: `Rs 1000`, `USD 250`
- Handle decimals and thousands separators: `$1,234.56`
- **Expected Output**: Amount + currency + numeric value columns

### Exercise 2.4: Multi-PII Detection
- Identify chats containing 2+ PII types
- Create a PII density score (PII items per message)
- Flag high-risk chats (3+ PII types)
- **Expected Output**: PII count + types present + risk level

### Exercise 2.5: URL & Domain Extraction
- Extract URLs: `http://example.com`, `https://site.co.in`
- Extract email domains: `@gmail.com`, `@company.co.in`
- Extract mentions of websites without protocols: `visit example.com`
- **Expected Output**: List of all URLs and domains

---

## 🔴 Level 3: ADVANCED REGEX EXERCISES

### Exercise 3.1: Comprehensive PII Redaction Function
Create a function that redacts:
- Names → `[NAME]`
- Emails → `[EMAIL]`
- Phones → `[PHONE]`
- All IDs → `[ID-TYPE]` (e.g., `[ORDER-ID]`)
- Addresses → `[ADDRESS]`
- Maintain message readability
- **Expected Output**: Fully anonymized message + PII log

### Exercise 3.2: Sentiment Pattern Matching
Build regex-based sentiment indicators:
- Positive words: "thank", "great", "excellent", "satisfied"
- Negative words: "not working", "disappointed", "frustrated", "angry"
- Intensity modifiers: "very", "extremely", "really"
- Negations: "not", "never", "no"
- **Expected Output**: Sentiment score + matching words + intensity level

### Exercise 3.3: Smart ID Categorization
- Detect and categorize ALL ID types automatically
- Validate ID formats (checksum if applicable)
- Extract metadata from IDs (date, region, type)
- Create ID hierarchy: Primary vs Secondary IDs
- **Expected Output**: ID taxonomy + validation status

### Exercise 3.4: Email Validation & Analysis
- Validate email format strictly (RFC 5322 compliant)
- Extract username and domain separately
- Categorize by domain type: free email vs corporate
- Detect suspicious email patterns
- **Expected Output**: Valid/invalid flag + email components + domain type

### Exercise 3.5: Complex Pattern Matching
- Extract address components (street, city, state, PIN)
- Parse product codes: `ABC-123-XL-RED`
- Extract credit card types from partial numbers (without full numbers)
- Parse structured data from free text
- **Expected Output**: Structured fields from unstructured text

---

## 🔵 Level 4: NLP TECHNIQUES

### Exercise 4.1: Text Preprocessing Pipeline
Create a complete preprocessing function:
- Lowercase conversion
- Remove special characters (keep relevant punctuation)
- Remove extra whitespace
- Handle contractions: "don't" → "do not"
- Remove/replace emojis
- **Expected Output**: Clean text + preprocessing stats

### Exercise 4.2: Advanced Stop Word Removal
- Remove standard stop words (NLTK/spaCy)
- Keep domain-specific important words ("order", "refund")
- Create custom stop word list for customer service
- Measure information retention after removal
- **Expected Output**: Filtered text + keyword density

### Exercise 4.3: Stemming vs Lemmatization
Compare results:
- Apply Porter/Snowball stemming
- Apply WordNet lemmatization
- Analyze differences in output
- Measure impact on word frequency
- **Expected Output**: Comparison table + recommendations

### Exercise 4.4: Named Entity Recognition (NER)
Use spaCy or NLTK:
- Extract PERSON, ORG, GPE, DATE, TIME entities
- Compare NER results with regex extraction
- Fine-tune NER for customer service domain
- Handle multi-word entities
- **Expected Output**: Entity table + confidence scores

### Exercise 4.5: Intent Classification
Build intent classifier:
- Classify queries: Refund, Cancel, Support, Info, Complaint
- Use TF-IDF + Logistic Regression
- Try keyword-based rules vs ML approach
- Measure accuracy against manual labels
- **Expected Output**: Intent labels + confidence + feature importance

### Exercise 4.6: Sentiment Analysis
Multiple approaches:
- Rule-based: VADER sentiment
- Lexicon-based: TextBlob
- ML-based: Train on labeled data
- Compare all three approaches
- **Expected Output**: Sentiment scores from each method + comparison

### Exercise 4.7: Topic Modeling
- Apply LDA (Latent Dirichlet Allocation)
- Extract main topics from queries
- Identify topic distribution per category
- Visualize topics
- **Expected Output**: Topic labels + keywords + distribution

### Exercise 4.8: Text Similarity
- Calculate cosine similarity between queries
- Find duplicate/similar complaints
- Group related issues
- Use TF-IDF or word embeddings
- **Expected Output**: Similarity matrix + query clusters

---

## 🎯 BONUS CHALLENGES

### Challenge 1: Real-Time PII Detector
Build a system that:
- Processes messages in real-time
- Flags PII before storage
- Suggests redactions
- Maintains audit log

### Challenge 2: Query Auto-Response System
Create a system that:
- Classifies query type
- Extracts key information
- Suggests template responses
- Learns from resolutions

### Challenge 3: Privacy Compliance Checker
Build a tool that:
- Scans conversations for PII
- Checks GDPR/privacy compliance
- Generates compliance reports
- Suggests anonymization strategies

### Challenge 4: Customer Journey Analyzer
Develop analytics for:
- Track issues per customer (using IDs)
- Identify repeat complainers
- Measure resolution time
- Predict escalation risk

---

## 📊 EVALUATION METRICS

For each exercise, measure:

### Regex Exercises:
- **Precision**: % of correct extractions
- **Recall**: % of missed items
- **F1 Score**: Harmonic mean of precision & recall

### NLP Exercises:
- **Accuracy**: Overall correctness
- **Processing Speed**: Time per document
- **Memory Usage**: Resource efficiency
- **Interpretability**: Can you explain the results?

---

## 🛠️ RECOMMENDED TOOLS

**Regex Testing:**
- regex101.com (interactive tester)
- regexr.com (visual builder)
- Python `re` module

**NLP Libraries:**
- spaCy (fast, production-ready)
- NLTK (educational, comprehensive)
- TextBlob (simple sentiment)
- Transformers (BERT, GPT for advanced)

**Data Analysis:**
- Pandas (data manipulation)
- Matplotlib/Seaborn (visualization)
- scikit-learn (ML algorithms)

---

## 📈 LEARNING PATH

**Week 1-2:** Complete all Level 1 exercises
**Week 3-4:** Complete all Level 2 exercises  
**Week 5-6:** Complete all Level 3 exercises
**Week 7-8:** Complete all Level 4 exercises
**Week 9-10:** Tackle bonus challenges

**Daily Practice:** Spend 30-60 minutes on one exercise
**Weekly Review:** Compare your solutions with online resources
**Monthly Project:** Combine multiple techniques into a mini-project

---

## 💡 SUCCESS TIPS

1. **Start Simple**: Don't jump to advanced exercises
2. **Test Incrementally**: Test each pattern on sample data
3. **Handle Edge Cases**: Empty strings, special characters, multiple matches
4. **Document Your Code**: Write comments explaining your regex
5. **Version Control**: Keep different versions of your patterns
6. **Benchmark**: Measure performance for each approach
7. **Iterate**: Continuously improve your patterns based on results

Good luck with your NLP learning journey! 🚀