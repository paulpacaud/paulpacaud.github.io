---
title: "TalimAI - AI-powered Job Interview Coach"
excerpt: "Fullstack web development of an application helping candidates prepare for their job interviews. <br/><br/><img src='/images/talimai_chatbot.PNG'>"
collection: portfolio
---

## Access the app here: <a href="https://talimai.com/landing-page">TalimAI</a>
( Note that the app is not yet responsive, thus not adapted to mobile devices )
<br/><img src='/images/landing_page_talimai.png'>

## Introduction

I'm super excited to unveil <a href="https://talimai.com/landing-page">TalimAI</a>, a novel approach to job interview preparation using generative AI. It’s not just a collection of interview questions as you may have already seen; It's a whole lot more – it’s a personalized coach that's designed to help candidates really really stand out.

Over the past year, we've engaged with numerous job seekers and they all share the same problem: it’s more and more difficult to stand out. Candidates usually prepare alone, with no feedback, and they are super stressed by getting an unexpected question.
That’s where TalimAI comes into the picture. Our coach leverages AI to make job seekers save time, save stress, and at the end, get their dream job.

The project is led by <a href="https://www.linkedin.com/in/antoinecarriere/">Antoine Carriere</a>, Sales Executive at Google, ex-BCG.

## The app

Basically, we’ve made the user experience straightforward:
- First, you provide the AI with a job title, company name, and job description.
- Then, you take a customized interview with tailored questions.
- At the end, you get a comprehensive feedback, so that you improve by each interview.

That being said, let me explain you how it works under the hood.

<br/><img src='/images/talimAI_Technical_Stack.png'>

#### Front End

The Front-end is written using Angular (combination of Typescript/HTML/CSS). The team works with Figma for the UI-UX design. 

#### Back End

The Back-end uses a NodeJS server, built using the framework Express.

We chose a cloud-hosted, NoSQL database built with Google Firestore.
Firebase also powers the authentication and hosting parts.

#### Continuous Integration and Deployment

Our development cycle is streamlined with GitHub CI/CD pipelines, ensuring that code updates are automatically and reliably deployed to production with minimal downtime. Every Pull Request is peer-reviewed.

#### AI models

##### Large Language Model powering the chatbot

The AI chatbot is built upon GPT-4. The code is written so as to be AI-provider agnostique: if tomorrow Anthropic or Google release better models, we can switch easily.

The LLM model is enhanced through a RAG (Retrieval-Augmented Generation) system, allowing us to extract from our huge database relevant data related to the job and company selected by the candidate. The dataset has been collected through homemade web scrappers.
To call GPT4, we chose to rely on the Azure API instead of the OpenAI's one because Azure provides a more robust and much faster response time (like x2 faster). 

Advanced prompt engineering methods are employed to maximize the LLM's alignment. We mainly rely on Prompt Compression (for reducing token-related costs), and Information re-ordering (to optimize the position of important details) based on <a href="https://www.microsoft.com/en-us/research/blog/llmlingua-innovating-llm-efficiency-with-prompt-compression/">Microsoft's LLMLingua’s framework</a>.

#### Text-to-Speech

The Text-to-Speech capabilities come from OpenAI Whisper.
The choice between Whisper and Eleven Labs was made taking into account that 11Labs's quality is better but Whisper's response time is faster, which is the priority for our real-time chatbot.

