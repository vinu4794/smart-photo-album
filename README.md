# Smart-photo-album Web App

Implement a Smart photo album web application, that can be searched using natural language processing through both text and voice using AWS Services

## Workflow:


Step 1: Open front end URL.
S3 Bucket (B1)- contains static website for our frontend UI.


Step 2: Upload Photos.
S3 Bucket (B2) used to store photos.
API Gateway enables photo to be uploaded to S3.
Lambda Function index-photos-b2 triggered to index Photo.


Step 3: Recognize Labels & add to ElasticSearch.
AWS Rekognition used.
A JSON object with a reference to each object in the S3 is stored in an ElasticSearch index.


Step 4: Train Lex Bot for utterances.
Train a lex bot to understand user queries related to showing photos.


Step 5: Get Images on frontend.
Input search query using Microphone (AWS Transcribe) or Text.
API Gateway enables search query to be sent to Lambda function.
Lambda function calls Lex bot.
Disambiguate user query using Lex to get labels.
Search for images with those labels in ElasticSearch table.
Display those images on UI.

## Front End UI:
![Front End UI](https://github.com/vinu4794/smart-photo-album/blob/main/images/ui.jpg)

## Architecture Flow:
![Architecture Flow](https://github.com/vinu4794/smart-photo-album/blob/main/images/architecture_Smart_photo_Album.png)


