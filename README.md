# SceneSense

**Natural-Language Retrieval of Relevant Moments from Long-Form Videos**  
**Submission:** 4th International AI Championship — Project Proposal  
**Project stage:** Implemented Minimum Viable Product (MVP)  
**Suggested category:** Intelligent App Creation *(confirm the exact option in the registration form)*

> **Find moments, not minutes.** SceneSense addresses a simple but costly problem: the information we need may be buried in hours of video, yet conventional navigation still makes us search for it manually.

![Figure 1: High-level architecture illustration](https://raw.githubusercontent.com/Huzaifa-Shabbir/Scene-Sense-Documentation/main/Architecture.png)

*Figure 1. High-level architecture illustration. The specific components used in the MVP should be checked against the implementation before submission.*

## 1. Project Overview & Problem Statement

Video is central to education, professional training, research, digital archives, media production, and operational review. However, video content is inherently sequential: even when a viewer knows what they want to find, locating a brief event can require watching, scrubbing, or replaying lengthy recordings. This problem grows as recordings become longer and collections expand.

Keyword search over titles and descriptions provides limited help. Speech transcripts improve discoverability but cannot consistently locate **visual events that are not spoken aloud**: a person entering a room, an object being moved, a specific action, or a scene transition. Basic frame-level matching can also lose the context needed to understand actions occurring over time.

**Problem statement:** How can a user describe a moment in natural language and retrieve the relevant portion of a long-form video without manually searching through the full recording?

**SceneSense** is an AI-focused final-year project addressing this problem through natural-language video retrieval, multimodal representations, and temporal search. The project has reached an **MVP implementation stage**. This proposal presents its intended end-to-end capability, underlying technical design, practical value, and next steps for validation and refinement.

## 2. Proposed Solution

SceneSense is designed to connect the meaning of a user's text query with the content of a video and identify the most relevant moments. Instead of asking users to know an exact timestamp, it aims to let them describe what they are looking for in ordinary language.

An illustrative query is: **“Find the moment when someone wearing a red shirt enters the room.”** A successful retrieval experience would surface the relevant time interval and allow the user to inspect the matching footage.

The system design has two complementary paths:

1. **Video preparation and indexing.** Video content is decoded or sampled, transformed into machine-readable visual representations, associated with time intervals, and made searchable.
2. **Query understanding and retrieval.** A natural-language query is interpreted and classified, compared with indexed video content, and used to rank candidate moments for review.

![Figure 2: Conceptual video indexing pipeline](https://raw.githubusercontent.com/Huzaifa-Shabbir/Scene-Sense-Documentation/main/Video%20Indexing.png)

*Figure 2. Conceptual video indexing pipeline.*

![Figure 3: Query processing and retrieval workflow](https://raw.githubusercontent.com/Huzaifa-Shabbir/Scene-Sense-Documentation/main/Queryprocessing.png)

*Figure 3. Query processing and retrieval workflow.*

### Technical approach and research basis

SceneSense draws on **vision-language alignment**, **semantic retrieval**, and **temporal video understanding**. Query classification is an important architectural consideration: an appearance-oriented request, an action-oriented request, and a temporally complex request can place different demands on retrieval. Classifying intent provides a basis for query-aware processing rather than treating every search as identical.

The research direction includes established ideas from **CLIP-style vision-language representations**, hierarchical video understanding, and efficient sequence modeling such as **Mamba**. Literature reviewed for the FYP includes **Hi-Mamba, EXPRT, and Video-ITG**. These are research influences and comparison candidates; their mention does **not** imply that every technique has been implemented in the MVP.

The distinguishing proposition is a **user-facing search experience for long videos** that combines natural-language input, query-aware processing, and retrieval of specific video moments rather than merely describing an entire video.

## 3. Objectives & Expected Outcomes

### Core objectives

- Reduce the effort required to find a described event in long video recordings.
- Develop an end-to-end foundation for video understanding and text-to-video-moment retrieval.
- Incorporate **query classification** into the retrieval design so that different search intents can be handled more appropriately.
- Preserve temporal context and associate search results with relevant video intervals.
- Provide an accessible demonstration of the retrieval experience.
- Evaluate retrieval relevance, temporal localization, efficiency, and usability with representative test cases.

### Current achievement and expected outcomes

**Confirmed current milestone:** An MVP of SceneSense has been implemented. The precise set of fully working features and any measured performance figures should be confirmed using the application itself before the final submission or live demonstration.

**Expected competition-ready outcomes:** A demonstrable application, documented architecture, example queries and results, a concise evaluation report, and a clear explanation of how the MVP can evolve into a more robust video-search tool.

Evaluation should include suitable measures such as **Recall@K** for retrieval, temporal overlap metrics where ground-truth intervals are available, response latency, and qualitative failure analysis. **No unverified accuracy, speedup, or benchmark result is claimed in this proposal.**

## 4. Target Users

| Target group | Problem addressed | Example |
|---|---|---|
| Researchers and analysts | Searching recorded experiments, interviews, or observations | Find a described event in a lengthy recording |
| Content creators and editors | Discovering relevant footage within large collections | Locate a scene containing a specific action |
| Video archive managers | Making stored footage more discoverable | Search visually meaningful moments without manual tagging |
| Operational reviewers | Narrowing down footage for subsequent human inspection | Surface candidate intervals matching a described activity |
| Students and educators | Revisiting a specific lesson or demonstration in a long lecture | Locate the moment an instructor draws a particular diagram |

SceneSense is intended to **assist human review**, not make definitive claims about individuals or incidents. Retrieved moments must be verified in sensitive contexts.

## 5. Key Features / Deliverables

The following table describes the **target MVP-to-competition functionality**. It is not a feature-by-feature audit of the currently deployed MVP; the implementation status should be verified against the actual project before public claims are made.

| Capability | Purpose | Deliverable / evidence |
|---|---|---|
| Video ingestion | Accept and prepare source footage | Supported input demonstration |
| Visual feature extraction | Represent meaningful video content | Documented processing pipeline |
| Time-aware indexing | Associate searchable content with video intervals | Indexed segment representation |
| Natural-language query input | Let users describe desired events | Search interface demonstration |
| Query classification | Identify query type to guide retrieval | Classifier design and example outputs |
| Semantic matching and ranking | Find candidate intervals relevant to the query | Ranked retrieval examples |
| Timestamped navigation | Let users inspect matching moments | Search-to-playback demonstration |
| Evaluation and documentation | Establish performance and limitations | Test cases, metrics, and technical report |

![Figure 4: Intended user journey](https://raw.githubusercontent.com/Huzaifa-Shabbir/Scene-Sense-Documentation/main/UserJourney.png)

*Figure 4. Intended user journey; not an application screenshot. Actual MVP screenshots should be added separately when available.*

## 6. Implementation Plan & Timeline

**Development status:** SceneSense has progressed beyond ideation and has an implemented MVP. The schedule below is a **proposed four-week competition-readiness and refinement plan**, not a claim about the dates or sequence of past development.

| Stage | Suggested period | Work | Output |
|---|---|---|---|
| MVP baseline | **Already achieved** | Initial implementation of SceneSense | Existing MVP |
| Verify and document | Week 1 | Audit implemented features, capture real screenshots, document dependencies and architecture | Verified feature matrix and demo evidence |
| Evaluate | Week 2 | Run representative queries, record results and latency, analyze failure cases | Evaluation summary |
| Improve | Week 3 | Prioritize reliability, retrieval quality, interface clarity, and resource efficiency | Refined MVP |
| Present and package | Week 4 | Prepare demonstration, repository documentation, reproducible setup instructions, and pitch | Competition-ready submission |

![Figure 5: Roadmap](https://raw.githubusercontent.com/Huzaifa-Shabbir/Scene-Sense-Documentation/main/Roadmap.jpg)

*Figure 5. Roadmap from implemented MVP toward a documented and validated competition demonstration.*

## 7. Resources or Requirements

**Technical resources:** A Python-based machine-learning environment is a practical fit for this problem domain, alongside video decoding tools, vision-language models, temporal indexing, and an application interface. Common options include PyTorch, OpenCV/FFmpeg, pretrained vision-language checkpoints, and vector similarity search. **These are illustrative technology options, not a verified inventory of the MVP's actual stack.**

**Compute and storage:** Video processing may require GPU acceleration, adequate storage for video assets and intermediate representations, and sufficient memory for model inference. Compute needs depend on video duration, sampling strategy, and model size.

**Data and testing:** Publicly available, appropriately licensed video retrieval or temporal grounding benchmarks can support repeatable evaluation. A small set of consented real-world videos can demonstrate practical use cases.

**Team capabilities:** Machine learning, computer vision, natural-language processing, software integration, interface development, evaluation, and technical documentation.

**Responsible deployment:** Appropriate rights to process videos, safeguards for sensitive footage, and clear communication that AI retrieval results may be imperfect.

## 8. Potential Challenges or Risks

| Challenge | Impact | Mitigation |
|---|---|---|
| Long-video processing cost | Increased inference time and memory use | Clip sampling, batching, caching, and efficient indexing |
| Complex or ambiguous language | Multiple plausible interpretations of a query | Query classification, ranked alternatives, and clearer query feedback |
| Brief or subtle events | Difficult temporal localization | Multi-scale temporal segments and candidate refinement |
| Domain variation | Performance differences across lectures, films, and operational footage | Evaluate across varied content and report limitations |
| Sparse evaluation labels | Difficult to quantify retrieval quality | Curate test cases and use suitable public benchmarks |
| Model hallucination or false matches | Users may trust irrelevant results | Show source video evidence and enable manual verification |
| Privacy and copyright | Sensitive or restricted footage | Use permitted datasets, protect access, and respect licensing |
| Integration and deployment | Component incompatibilities or resource constraints | Modular design, baseline testing, and staged optimization |

## 9. Additional Details (Optional)

### Innovation and relevance

SceneSense focuses on a widely encountered yet underserved interaction: **asking a video a question about what can be seen and receiving a specific moment as the answer**. The project combines ideas from multimodal retrieval, query understanding, and temporal modeling in a practical application context.

### Example demonstration scenario

A user has a long video and wants to find a short event. Rather than dragging the playback bar repeatedly, they enter a description such as **“Show where the presenter places the device on the table.”** SceneSense is intended to identify and rank matching intervals so the user can inspect them directly. This is an **illustrative example**, not a verified benchmark result.

### Evidence and evaluation plan

The GitHub supporting-materials repository will contain architecture diagrams and this proposal. To strengthen the submission, the team should add **real MVP screenshots**, a **short recorded demo**, **sample queries with actual results**, and **measured evaluation figures** once verified. These artifacts will make it easier for judges to distinguish demonstrated functionality from planned improvements.

### Future potential

Potential extensions include search across multiple videos, better handling of complex event descriptions, more efficient indexing, and domain-specific adaptation. These are future opportunities rather than current MVP claims.

---

**Keywords:** Multimodal AI · Natural-Language Video Retrieval · Computer Vision · Temporal Video Understanding · Semantic Search

**Project status note:** The MVP implementation is confirmed by the project team. Detailed functionality, exact technologies, and quantitative performance should be validated against the source code and demonstration before external publication.
