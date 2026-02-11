# LABEEB — AI & Blockchain Powered Academic Guidance  
*by Reema F. Almukhlifi | Graduation Project*

> LABEEB was created to make academic and career decisions clearer, smarter, and verifiable for students before university.  
> The platform adapts learning materials dynamically according to each student’s learnability style, while securing achievements through blockchain-backed credentials.

---

## Project Overview  
**LABEEB** is a data-driven academic platform designed for pre-university students.

Students often face fragmented advising systems, unclear pathways, and unverifiable achievements. LABEEB replaces traditional static counseling with intelligent profiling, AI-generated insights, and tamper-proof certification.

The platform enables:

- understanding student abilities  
- mapping strengths to majors and careers  
- documenting achievements securely  
- making records trusted and instantly verifiable  

---

## Key Features  
- AI-powered academic & career recommendations  
- Adaptive learning materials based on individual learnability styles
- Learning-style and performance analytics  
- Personalized course & content suggestions  
- NFT-based digital certificates  
- Blockchain verification of credentials  
- LMS integration  
- Digital achievement portfolios  
- Role-based access control  
- Wallet-based ownership of certificates  
- Cross-platform access

---

## Responsibilities & Contributions (Reema)  
- Originated the core idea and defined the system mission.  
- Established product direction and long-term scalability vision.  
- Built and coordinated the project team.  
- Led planning, prioritization, and cross-member alignment.  
- Translated student pain points into system requirements.  
- Oversaw integration between AI, backend, and blockchain.  
- Ensured outputs serve real educational decision-making.  
- Led documentation, analysis, and graduation deliverables.  
- Contributed to pitching, evaluation, and future incubation readiness.

---

## System Architecture  

LABEEB follows a multi-layer architecture:

### 1. Presentation Layer  
Mobile/Web interfaces built using Flutter.  
Provides dashboards, recommendations, assessments, and certificate access.

### 2. Application Layer  
PHP (Laravel) backend handling:
- authentication  
- profile management  
- AI requests  
- course logic  
- certificate generation  

### 3. Data Layer  
MySQL & MongoDB for structured and semi-structured data.

### 4. Decentralized Layer  
Smart contracts on Polygon + file storage on IPFS.

---

## AI Decision Pipeline  

1. Student submits profile, interests, and assessments.  
2. Backend structures data for analysis.  
3. OpenAI API evaluates patterns & learning indicators.  
4. System generates:
   - recommended majors  
   - skills to develop  
   - suitable resources  
5. Results are stored and continuously refined.

Goal → dynamic, adaptive guidance rather than one-time advice.

---

## Adaptive Learning Model  

LABEEB does not only recommend what a student should study.  
It also adapts **how** the student learns.

Using AI analysis of assessments, behavior, and interaction patterns, the system identifies preferred learning styles (visual, auditory, reading/writing, practical, etc.).

Based on this detection, LABEEB dynamically modifies:

- recommended resources  
- explanation formats  
- video vs text balance  
- practice intensity  
- difficulty progression  

This creates a continuously evolving experience where content delivery matches the student’s cognitive preferences.

Outcome → higher comprehension, faster progress, and reduced decision anxiety.

---

## Blockchain & NFT Flow  

1. Student completes course or milestone.  
2. Certificate is generated.  
3. SHA-256 hash is created.  
4. File uploaded to IPFS → CID produced.  
5. Smart contract binds:
   - student ID  
   - certificate metadata  
   - CID  
6. NFT becomes verifiable through wallet access.

Outcome → instant trust without intermediaries.

---

## Tools & Technologies  

### Core  
- AI recommendation engine  
- NFT certification  
- Decentralized validation  
- LMS connectivity  

### Blockchain & Storage  
- Polygon  
- IPFS  
- Solidity  
- MetaMask  
- Alchemy  

### AI & APIs  
- OpenAI API  
- YouTube API  

### Backend  
- PHP (Laravel)  
- MySQL  

### Frontend  
- Flutter & Dart  

### Development  
- Python  
- Swift  
- C++  
- VS Code  
- Xcode  

### Design & Presentation  
- Figma  
- Keynote  
- Canva  

---

## System Infrastructure / Hardware  
- AWS EC2  
- MongoDB  

**Development Machines:** Intel i9, RTX 4090  
**Client Devices:** iOS / Android / Windows / macOS

---

## Security Model  
- HTTPS communication  
- token-based authentication  
- wallet ownership for certificates  
- blockchain immutability  
- IPFS hash validation  
- role-based permissions  

---

## Data Governance  
LABEEB minimizes stored sensitive information and separates:

- identity data  
- academic progress  
- credential proofs  

Blockchain is used only for verification, not raw personal data.

---

## Test Coverage  
The system has been validated through:

- unit tests  
- functional workflows  
- end-to-end verification  
- blockchain registration  
- AI response validation  

Major flows tested:
login → profiling → AI analysis → learning → certificate → NFT verification.

---

## Future Roadmap  
- national integration with schools  
- university admission linkage  
- employer verification portals  
- predictive labor-market alignment  
- scholarship matching  
- multilingual expansion  
- analytics dashboards for policymakers  

---

## Contact  
- GitHub: [iRemaF](https://github.com/iRemaF)  
- LinkedIn: [Reema F. Almukhlifi](https://www.linkedin.com/in/reema-f-almukhlifi-bbb2b1240/)  
