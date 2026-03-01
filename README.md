# AI Blog Importer Plugin

## Description
INT AI Blog Importer is a WordPress plugin that generates blog posts using an AI service and automatically creates a new post in draft or publish mode.

The plugin integrates WordPress core APIs with an external AI API to dynamically generate structured blog content based on a given topic.

## Features
- Custom admin page with topic input form
- Separate settings page to store API key
- AI-generated:
  - Title
  - Body content
  - Tags (comma separated)
- Automatically creates WordPress post
- Option to save as Draft or Publish
- Error message if API key is missing
- Error handling for failed API requests
- Uses WordPress core functions (wp_insert_post, wp_set_post_tags)

## Installation
1. Upload the `int-ai-blog-importer` folder to `/wp-content/plugins/`
2. Activate the plugin from WordPress Admin → Plugins
3. Go to "INT AI Blog Importer → Settings"
4. Enter your OpenAI API Key and save
5. Go to "INT AI Blog Importer" in dashboard
6. Enter topic and generate post

## Requirements
- WordPress 5.0+
- PHP 7.4+
- Valid OpenAI API Key
- Hosting that allows outbound API requests

## How It Works
1. User enters a topic in the admin page.
2. The plugin sends a structured prompt to the AI API using WordPress HTTP API.
3. AI returns Title, Content, and Tags.
4. The plugin parses the response.
5. WordPress creates a new post using core APIs.

## Prompt Design

The prompt instructs the AI to return structured output in a predictable format:

Generate a blog post for the topic: {topic}
Return strictly in this format:

Title:
Content:
Tags (comma separated)

This structure ensures:
- Consistent formatting
- Easier parsing in PHP using regex
- Reduced ambiguity in AI responses
- Reliable automation of post creation

## Plugin Structure

int-ai-blog-importer/
├── int-ai-blog-importer.php
├── includes/
│   └── int-ai-api-handler.php
└── README.md

## Assignment Coverage

✔ Basic plugin structure  
✔ WordPress Admin page  
✔ AI service integration  
✔ Post creation using WordPress APIs  
✔ Draft / Publish option  
✔ API key configuration  
✔ Structured prompt design  
