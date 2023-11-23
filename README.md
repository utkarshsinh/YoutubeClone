

# Simplified YouTube-Like Platform Design Overview
## Introduction
In my Full Stack Development learning, I embarked on creating a simplified version of a platform akin to YouTube. This project's intent was to replicate the fundamental features of YouTube, focusing on a basic yet functional framework rather than an exact replica.

## Objective
My primary objective was to learn and implement the core features of a video-sharing platform, with an emphasis on simplicity and scalability aspects, rather than creating a fully-fledged, production-level application.

## Background
Inspired by YouTube's functionality, which includes a range of complex features like video sharing, viewing, rating, and commenting by a vast user base, this project narrows its focus. The primary functionalities developed were video uploading and viewing.

## Requirements

* Google account integration for user sign-in/out.
* Video upload functionality for signed-in users.
* Transcoding of videos into various formats (e.g., 360p, 720p).
* Ability for all users to view a list of uploaded videos and watch individual videos.
## High-Level Design Overview
The design incorporates a range of cloud services for efficient video management and streaming:

* Video Storage: Utilizing Google Cloud Storage for both raw and processed video storage, ensuring scalability and cost-effectiveness.
* Video Upload Management: Implementing Cloud Pub/Sub for durable video upload events and asynchronous processing.
* Video Processing: Employing Cloud Run with ffmpeg for video transcoding, catering to fluctuating processing demands.
* Video Metadata Management: Using Firestore to store video metadata for display in the web client.
* API for Videos: Developing a straightforward API with Firebase Functions for video uploads and metadata retrieval.
* Web Client Interface: Creating a user interface with Next.js, hosted on Cloud Run, for video uploading and viewing.
* User Authentication: Integrating Firebase Auth for secure and convenient user authentication using Google Sign In.
## Detailed Design Aspects

1. **User Registration and Management:**  Leveraging Firebase Auth for user sign-up via Google accounts, with Firestore to maintain additional user details.
2. **Secure Video Upload Process:** Ensuring authenticated video uploads through signed URLs provided by Google Cloud Storage, managed via Firebase Functions.
3. **Asynchronous Video Processing:** Utilizing Cloud Pub/Sub as a messaging queue for managing video processing workloads and ensuring scalability.
## Considerations and Limitations
The design acknowledges certain limitations, like Cloud Run's request timeout and Pub/Sub's message redelivery, along with an absence of content legality checks. Future work is focused on addressing these limitations and expanding functionality.

## References and Further Reading
Included are references to various technologies used, such as Firebase Auth, Cloud Storage, and Cloud Run, providing a foundation for understanding the underlying technologies of this project.

* Firebase Auth: https://firebase.google.com/docs/auth
* Cloud Storage Signed URLs: https://cloud.google.com/storage/docs/access-control/signed-urls
* Pub/Sub Push subscriptions: https://cloud.google.com/pubsub/docs/push
* Using Pub/Sub with Cloud Storage: https://cloud.google.com/storage/docs/pubsub-notifications
* Using Pub/Sub with Cloud Run: https://cloud.google.com/run/docs/tutorials/pubsub
