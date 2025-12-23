# GitHub Storage Configuration Guide

This guide explains how to configure the China Travel Guide website to use GitHub for storing user contributions.

## Features

- Users can upload travel photos and comments without logging in
- All data is stored directly in a GitHub repository
- Simple configuration with minimal setup

## Configuration Steps

### 1. Create a GitHub Repository

1. Create a new public GitHub repository (recommended name: `china-travel-guide-data`)
2. Create these directories in the repository:
   - `data/` - for JSON data files
   - `images/` - for user photos

### 2. Create a GitHub Token

1. Go to GitHub Settings > Developer settings > Personal access tokens
2. Generate a new token with appropriate permissions
3. Copy the token (it will only be shown once)

### 3. Configure the Website

1. Open `index.html` file
2. Find the configuration section:

```javascript
const GITHUB_REPO_OWNER = 'YOUR_GITHUB_USERNAME';
const GITHUB_REPO_NAME = 'china-travel-guide-data';
const GITHUB_TOKEN = 'YOUR_GITHUB_TOKEN';
```

3. Replace these values with your GitHub username and token

## Usage

After configuration:
1. Users can submit photos and comments through the contribution form
2. Submitted content appears in the contributions list and photo wall
3. All data is stored in your GitHub repository

## Data Structure

User contributions are stored in `data/user-contributions.json`:

```json
[
  {
    "id": "unique-id",
    "author": "anonymous-user",
    "authorAvatar": "avatar-url",
    "city": "beijing",
    "spot": "Great Wall",
    "comment": "Amazing experience!",
    "imageUrl": "photo-url",
    "createdAt": "2024-01-01T12:00:00.000Z",
    "githubUrl": "#"
  }
]
```

## Troubleshooting

- Check browser console for error messages
- Verify GitHub token is valid and has correct permissions
- Ensure repository name and owner are configured correctly