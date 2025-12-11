# RenovAI  
## Public Repository Documentation  
## Proof of Concept Summary – Module Completion

RenovAI is a proof-of-concept system designed to help non-experts plan residential renovations one room at a time using multimodal artificial intelligence. The goal is to give everyday users the ability to understand layouts, test design variations, and preview realistic proposals without relying exclusively on professional designers or contractors.  

This documentation summarizes the work developed throughout the module, the experiments conducted, the technologies explored, the results achieved, and the limitations identified. Sensitive information, internal credentials, and proprietary details have been removed.

The live prototype website is available at: **https://www.renovai.ia.br**

---

# 1. Project Overview

RenovAI combines multiple technologies to support the early stages of renovation planning:

- Natural-language understanding for capturing user requirements  
- Generative image models for visual proposals  
- Structured layout reasoning for room configuration  
- A-Frame for interactive 3D visualization and AR/VR exploration  
- A step-by-step web interface designed for non-technical users  

The overarching idea is that users can upload photos, describe their preferences, and receive design suggestions, layout proposals, and supporting visualizations.

---

# 2. Core Components Developed in This Module

### 2.1 Generative Image Exploration
The project tested multiple image generation providers, including:

- Google Gemini (>= 1.5 series)  
- OpenAI GPT models with image generation  
- Stable Diffusion XL  

Key findings:

- **Gemini** performed well in spatial consistency and layout reasoning.  
- **OpenAI** produced high-quality, polished designs but occasionally introduced geometric distortions.  
- **SDXL** served as a stable fallback option.  

A complete multimodal notebook was built to support experimentation with prompts, image consistency, and perspective/top-view generation.

---

### 2.2 Layout Specification and Structured Reasoning

A custom “Layout Specification Agent” was implemented:

- Converts user input into a structured JSON description of the room  
- Defines zones (sleeping, working, living)  
- Allocates furniture categories  
- Describes spatial constraints and wall relationships  
- Serves as the intermediate layer for generating A-Frame environments  

This was a key advancement: the system can reason about space before generating visuals.

---

### 2.3 Automated A-Frame Environment Generation

The project validated the use of **A-Frame** for real-time 3D and optional AR/VR support.  
A programmatic HTML generator was created:

- Builds floors, ceilings, walls, lighting  
- Places furniture from a predefined asset catalog  
- Supports camera navigation and movement controls  
- Produces scenes that directly reflect the AI-generated layout specification  

This confirmed that room scenes can be created dynamically without manual modeling.

---

### 2.4 Asset Catalog Prototype

An initial asset catalog was built to reference available GLB models:

- Basic furniture items (bed, nightstand, desk, chair, couch, TV, plants)  
- Metadata for each item: scale, recommended positioning, category  

The catalog is not yet connected to real commercial furniture sources, but the internal structure demonstrates how a scalable system could operate.

---

### 2.5 Public Website (RenovAI)

A functional website was built to allow users to:

- Upload images  
- Answer project-related questions  
- Choose between “Edit Existing Photo” or “Generate New Inspiration”  
- View original and generated images side by side  
- Experience a simple interface focused on everyday consumers  

The website currently supports image generation and user guidance but does not yet integrate the full conversational LLM or the 3D generation pipeline.

Live prototype: **https://www.renovai.ia.br**

---

# 3. Results Achieved

### 3.1 Functional End-to-End Flow
The multimodal pipeline is capable of:

1. Receiving a natural-language description  
2. Translating it into a structured spatial layout  
3. Generating an A-Frame HTML scene  
4. Producing photo-realistic design proposals  
5. Displaying results in a user-friendly interface  

This demonstrates the technical feasibility of RenovAI as a renovation assistant powered by AI.

---

### 3.2 Image Generation Quality
Results were visually compelling, especially when:

- Prompts were explicitly structured  
- Object placement cues were provided  
- Top-view and perspective prompts were separated  

The generated designs often aligned well with the intended layout.

---

### 3.3 3D/AR/VR Validation
Using A-Frame, the PoC validated that:

- Real-time room reconstruction is possible in the browser  
- Furniture positioning can be automated  
- AR and VR modes are natively supported and can be enabled in future iterations  

While not integrated into the website, the experiments proved the approach is technically viable.

---

# 4. Limitations and Challenges

### 4.1 Generation Latency
Image generation takes several seconds depending on the provider.  
This affects user experience when running in a live web application.

### 4.2 No Integrated Conversational Assistant Yet
The RenovAI website does not yet include:

- A chat-based assistant  
- Stepwise conversational refinement  
- LLM-guided clarification questions  

This was partially developed in notebooks but not deployed in the frontend.

### 4.3 Asset Catalog Still Prototype-Level
The PoC uses generic GLB models rather than a real furniture database.

Limitations include:

- No real product dimensions  
- No pricing information  
- No connection to stores or suppliers  

### 4.4 Incomplete Integration Between Systems
The final website currently integrates:

- Image generation  
- User input flow  
- Design proposals  

But it does not yet integrate:

- The JSON layout generator  
- The full A-Frame 3D scene builder  
- Multimodal reasoning and iterative refinement  

### 4.5 Rendering Inconsistencies in A-Frame
During testing:

- Some models had incorrect default scales  
- Furniture alignment required manual adjustment  
- Room boundaries were sometimes crossed due to model dimensions  

These are not failures but expected challenges in early AR/VR prototyping.

---

# 5. Technical Experiments That Failed or Required Revision

This PoC intentionally includes notes about what did not work initially:

- Some generative models wrote text or labels inside images, requiring rewriting of prompts.  
- AR/VR rendering initially suffered from incorrect axes, inverted rotations and object clipping.  
- Gemini’s API occasionally returned format errors for multimodal tasks.  
- The first website template produced by the builder incorrectly assumed the platform was for construction professionals.  
  This required re-prompting and redesign.  

Documenting failures is essential to show how the system evolved.

---

# 6. Notebooks Developed

Throughout the module, several notebooks were produced:

- Generative image comparison  
- Layout reasoning and JSON specification  
- A-Frame automatic code generation  
- Multimodal orchestration tests (GPT + Gemini + SDXL)  
- Failure analysis notebooks for debugging model limitations  

These notebooks form the technical backbone of the PoC.

---

# 7. Conclusion

The RenovAI project successfully demonstrated that:

- Natural-language renovation planning is feasible  
- Generative models can produce coherent design proposals  
- Layout reasoning can be formalized in structured formats  
- A-Frame is an effective mechanism for interactive 3D and AR/VR scenes  
- A complete user-facing prototype can be deployed as a functional website  

The PoC delivered significantly more than a theoretical study.  
It produced a working prototype, validated multi-model generation, demonstrated spatial reasoning and confirmed the viability of browser-based 3D reconstruction.

---

# 8. Public Links

Live site: **https://www.renovai.ia.br**


