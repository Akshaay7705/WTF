1st PLACE IS OURS!


1️⃣ Is This Doable by May 17th?
✅ Yes, but with a focused approach. Given the timeframe (~6 weeks), we should prioritize core features and build a functional prototype rather than a full-fledged production system.

🚀 Recommended MVP (Minimum Viable Product) for the Hackathon:

Web-based interview platform (React + Node.js/Python)
Network monitoring for DNS queries (Python + Scapy)
AI analysis of user queries (LLM-based matching)
Real-time alerts for suspicious behavior
If time allows, we can add browser monitoring (tab-switch detection, copy-paste blocking).

2️⃣ What Should You Learn?
Since this project involves web development, network security, and AI, your team should focus on:

Component	Technology to Learn	Why?
Frontend	React.js, WebSockets	For the interview UI and real-time alerts
Backend	Node.js (Express) or Python (FastAPI)	To manage interviews, logging, and API calls
Database	PostgreSQL / Firebase / MongoDB	To store logs and interview data
Network Monitoring	Python (Scapy, PyShark), Pi-hole	To capture and analyze DNS queries
Firewall/DNS Control	Linux (iptables, dnsmasq)	To block or redirect searches
AI Query Analysis	OpenAI API / Local NLP models (spaCy, Hugging Face)	To detect if a student’s search matches test questions
Real-time Alerts	WebSockets, Redis, Kafka	To send notifications to admins
You don’t need deep expertise in all these, but knowing basic Python networking, API integration, and AI models will be helpful.

3️⃣ AI Integration: Matching Queries with Test Questions
To detect cheating, we can use AI to compare search queries against exam questions.

Approach:

Capture the search query from DNS logs or browser monitoring.
Use NLP (Natural Language Processing) to check if the query is similar to a test question.
If similarity > threshold (e.g., 80%), flag it as a cheating attempt.
AI Model Choices:

Fast & Simple → spaCy + fuzzywuzzy for basic text similarity
Better Accuracy → Sentence Transformers (all-MiniLM-L6-v2)
Advanced → OpenAI’s GPT API (text-embedding-ada-002 for vector similarity)
Example: AI Similarity Check in Python

from sentence_transformers import SentenceTransformer, util

model = SentenceTransformer('all-MiniLM-L6-v2')

def is_cheating(search_query, exam_questions):
    query_embedding = model.encode(search_query, convert_to_tensor=True)
    for question in exam_questions:
        question_embedding = model.encode(question, convert_to_tensor=True)
        similarity = util.pytorch_cos_sim(query_embedding, question_embedding).item()
        if similarity > 0.8:  # 80% match threshold
            return True
    return False

# Example usage
exam_questions = ["What is Newton's second law?", "Explain photosynthesis."]
search_query = "formula for Newton's second law"
print(is_cheating(search_query, exam_questions))  # Output: True/False
✅ What This Does:

Converts exam questions and search queries into AI embeddings.
Computes cosine similarity to check for a match.
Flags cheating attempts if similarity is high.
📅 Next Steps (Week-by-Week Plan)
Week	Tasks
April 1 - 7	Finalize tech stack, set up the repo, and create a basic interview UI.
April 8 - 14	Implement DNS monitoring (capture & log search queries).
April 15 - 21	Develop AI query matching for cheating detection.
April 22 - 28	Integrate real-time alerts (WebSockets, notifications).
April 29 - May 5	Improve UI/UX, test AI accuracy, refine monitoring.
May 6 - 12	Add finishing touches, optimize performance.
May 13 - 17	Final testing, bug fixes, prepare for hackathon.
💡 Questions for You:
What tech stack are you comfortable with? (React, Node.js, Python, etc.)
Would you like a starter template for the interview platform?
Do you need help setting up AI query matching or DNS logging first?
Let’s get started! 🚀



