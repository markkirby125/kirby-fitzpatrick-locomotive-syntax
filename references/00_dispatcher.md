# Locomotive Syntax Engine — Technical Operational Dispatcher

**Framework Author**: William Fitzpatrick (*Writer Science*)  
**Source Lecture**: [20 Years of Writing Advice in 52 mins](https://www.youtube.com/watch?v=G-Sl0-PZv2Q)  
**Parent Collection**: [Master Collection](../../kirby-fitzpatrick-writers-collection/SKILL.md) | [Global Help](../../../kirby-help/SKILL.md)  

---

## 1. Cognitive Foundation: The Locomotive Principle

Human short-term working memory cannot evaluate semantic conditions without first knowing **who is acting** and **what they are doing**. When technical writing front-loads subordinate clauses, dependencies, and qualifications before the primary subject-verb pair, reader comprehension stalls.

```text
[Pre-modifier Bloat / Suspended Attention]
"Under high concurrent write throughput across distributed shards when quorum is degraded, the ingest worker crashes."
                                                                                         ^^^^^^^^^^^^^^^^^^^^
                                                                                         Locomotive Engine (Buried)

[Locomotive Engine Front-Loaded]
"The ingest worker crashes when quorum degrades under high write throughput."
 ^^^^^^^^^^^^^^^^^^^^^^^^^
 Locomotive Engine (First 4 words)
```

In the **Locomotive Syntax** framework, every high-impact technical sentence is engineered like a train:
1. **The Locomotive (Engine)**: The primary subject-verb nexus placed within the first 5–7 words.
2. **The Boxcars (Payload)**: Qualifying clauses, conditions, operational boundaries, and contextual details hitched behind the locomotive.

---

## 2. Core Transformation Rules

### Rule 1: The 7-Word Engine Invariant
The primary agent (subject) and core transformation (verb) must land within the first 7 words of the sentence. Never delay the subject past word 7.

### Rule 2: Unhitch Pre-Modifier Freight
Identify introductory prepositional phrases or conditional preambles exceeding 5 words. Move them to the trailing position (trailing boxcars) or split into two sentences.

* **Anti-Pattern**: *"In accordance with the new transactional retry policy established in RFC 402, the database client terminates orphaned pool connections."* (19 words before subject)
* **Locomotive Fix**: *"The database client terminates orphaned pool connections, complying with the RFC 402 retry policy."*

### Rule 3: Rescue the Buried Predicate
When a sentence uses a hollow placeholder ("There is", "It has been determined that") to hide the real actor and action:
* **Anti-Pattern**: *"There is a race condition that causes data loss when multiple threads mutate the cache concurrently."*
* **Locomotive Fix**: *"Concurrent thread mutations corrupt the cache during write races."*

---

## 3. Contextual Application Matrix

### 3.1 Code Review Comments
* **Slop**: *"While investigating the memory profile under load test scenario B, it seems this buffer allocation leaks 4MB per request."*
* **Locomotive**: *"This buffer allocation leaks 4MB per request under load test scenario B."*

### 3.2 Pull Request Descriptions
* **Slop**: *"To ensure backward compatibility across all v2 microservice clients without breaking the gateway contract, we added an optional tenant_id parameter."*
* **Locomotive**: *"We added an optional `tenant_id` parameter to preserve backward compatibility for v2 clients."*

### 3.3 Architecture Decision Records (ADRs)
* **Slop**: *"Due to high p99 tail latency incurred by synchronous RPC serialization overhead during peak traffic, Kafka is adopted for event ingestion."*
* **Locomotive**: *"We adopted Kafka for event ingestion to reduce p99 tail latency caused by synchronous RPC overhead."*

---

## 4. Verification & Audit Checklist

- [ ] Does the sentence establish its subject and verb within the first 7 words?
- [ ] Are introductory clauses $\le 5$ words?
- [ ] Are qualifications and exceptions trailing behind the main clause rather than preceding it?
- [ ] Are empty lead-ins ("It is evident that", "There are several reasons why") eradicated?
