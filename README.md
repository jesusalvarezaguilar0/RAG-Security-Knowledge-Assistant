# RAG Security Knowledge Assistant

## Overview

The RAG Security Knowledge Assistant is a Retrieval-Augmented Generation (RAG) chatbot designed to answer cybersecurity questions using MITRE ATT&CK knowledge sources. Instead of relying solely on a large language model's general knowledge, the chatbot retrieves relevant information from a cybersecurity document collection and uses that context to generate more accurate responses.

This project demonstrates how retrieval systems can improve the reliability of AI-generated answers and reduce hallucinations when working with domain-specific cybersecurity information.

---

## Problem Statement

Security analysts often need to search through large amounts of threat intelligence and MITRE ATT&CK documentation to understand attacker techniques and tactics. Finding relevant information manually can be time-consuming and inefficient.

This project explores how Retrieval-Augmented Generation (RAG) can help analysts quickly obtain relevant cybersecurity information by combining document retrieval with large language model reasoning.

---

## Technologies Used

- Flowise
- Groq API
- Llama 3.3 70B Versatile
- Hugging Face Embeddings
- sentence-transformers/all-MiniLM-L6-v2
- In-Memory Vector Store
- Retrieval-Augmented Generation (RAG)
- MITRE ATT&CK Framework

---

## System Architecture

1. User submits a cybersecurity question.
2. The question is converted into embeddings.
3. Relevant document chunks are retrieved from the vector store.
4. Retrieved context is sent to the LLM.
5. The LLM generates a response using the retrieved information.
6. The final answer is returned to the user.

---

## Knowledge Base

The chatbot was built using MITRE ATT&CK-related documents covering:

- Initial Access
- Credential Access
- Lateral Movement

Example topics included:

- Valid Accounts
- Additional Cloud Credentials
- Brute Force Attacks
- Remote Desktop Protocol (RDP)
- Evil Twin Wireless Attacks

---

## Example Questions Tested

- How can valid cloud accounts be used by adversaries to achieve persistence or lateral movement?
- What are different ways attackers can gain initial access through Wi-Fi networks?
- How does brute force password guessing work?
- How can attackers use Remote Desktop Protocol (RDP) for lateral movement?
- What is a trusted relationship attack?

---

## Evaluation Results

The chatbot successfully answered most questions using information retrieved from the supplied cybersecurity documents.

### Successful Behaviors

- Retrieved accurate information from MITRE ATT&CK documents
- Referenced relevant cybersecurity techniques
- Refused unrelated questions such as weather requests
- Generated detailed responses for documented attack techniques

### Limitations Observed

- Occasionally produced answers based on general model knowledge when information was not present in the documents
- Higher temperature settings increased hallucination risk
- Larger retrieval settings sometimes introduced redundant information

---

## Parameter Experiments

### Temperature

- 0.3: More focused and grounded responses
- 0.7: More detailed but increased hallucination risk

### Chunk Size

- 1000: Broader context retrieval
- 500: More precise and focused retrieval

### Top K

- 4: Concise responses
- 6: More detailed responses with some repetition

---

## What I Learned

This project taught me how Retrieval-Augmented Generation differs from traditional prompting. I learned that the quality of document retrieval has a major impact on answer quality and that tuning chunk size, retrieval settings, and temperature can significantly affect performance. Through testing and evaluation, I gained hands-on experience building AI systems that combine knowledge retrieval with language model reasoning.

---

## Future Improvements

- Expand the cybersecurity knowledge base
- Add CVE and threat intelligence feeds
- Implement source citations
- Improve hallucination prevention
- Deploy as a cybersecurity analyst assistant

---

## Demo

Flowise Chatbot:

https://cloud.flowiseai.com/chatbot/7f436a8e-24f9-473a-8f23-1adfcf8c4187
