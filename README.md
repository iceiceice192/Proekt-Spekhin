# Final Project - SlovoVed
## SlovoVed is an intelligent virtual assistant designed to help users learn spoken Russian through natural and interactive dialogue. By leveraging Natural Language Processing (NLP) and Artificial Intelligence (AI) technologies, SlovoVed creates a realistic conversational experience for learners of Russian as a foreign language.

## Motivation & Relevance
Learning spoken Russian can be a challenging task, especially without access to native speakers or dynamic conversational practice. Traditional language learning apps often lack true interactivity and contextual awareness.

SlovoVed addresses this gap by enabling voice-based interaction with an AI tutor, offering real-time feedback, natural dialogue generation, and a personalized language learning experience.

## Purpose
The goal of SlovoVed is to provide a realistic simulation of conversational Russian using cutting-edge AI tools. Users can speak to the assistant, receive context-aware responses, and thus gradually develop fluency, pronunciation accuracy, and confidence in conversation.

## Technologies Used
To achieve this, SlovoVed integrates the following NLP and AI components:

### 1. Speech Recognition (ASR) – OpenAI Whisper

asr_pipeline = pipeline(
    "automatic-speech-recognition",
    model="openai/whisper-medium",
    device=device
)
Transcribes user’s spoken input into text.

Robust against noise and accents.

### 2. Dialogue Generation – Saiga LLaMA 3 (IlyaGusev/saiga_llama3_8b)

chat_pipeline = pipeline(
    "text-generation",
    model="IlyaGusev/saiga_llama3_8b",
    device_map="auto",
    torch_dtype=torch.float16
)
Produces natural, coherent Russian responses based on user input.

Capable of handling casual conversation and varying contexts.

### 3. Text-to-Speech (TTS) – gTTS (Google Text-to-Speech)

from gtts import gTTS
Converts generated text responses back into audio.

Provides a fully voice-based, bidirectional communication loop.

## System Architecture

[User Speech]
     ↓
[ASR: Whisper]
     ↓
[Text Input]
     ↓
[Dialogue Model: Saiga LLaMA3]
     ↓
[Text Response]
     ↓
[TTS: gTTS]
     ↓
[Audio Output]
This pipeline creates a seamless audio-dialogue system, enabling the user to both speak and hear responses naturally.

## Results & Observations
Whisper reliably transcribes diverse spoken Russian inputs.

The Saiga model generates fluent, appropriate, and engaging responses.

gTTS provides natural-sounding Russian voice output.

The system successfully simulates live spoken conversation in Russian.

## Future Perspectives
Improved TTS with voice customization and emotional tone control.

Integration of speech error detection and correction.

Vocabulary tracking and adaptive content recommendations.

Cross-language interaction and multilingual dialogue support.

Web/mobile interface for greater accessibility.

SlovoVed merges the power of ASR, conversational AI, and speech synthesis to create a truly interactive Russian learning assistant. It brings users closer to the experience of real-life conversation, helping bridge the gap between learning and using the language.
Adaptive curriculum based on user proficiency and progress. Gamified elements and real-life situational dialogue scenarios. Support for multilingual learners and speech error correction.
