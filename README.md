# gatsby-twitter-github-charts

# 🚀 Javascript full-stack 🚀

https://github.com/coding-to-music/gatsby-twitter-github-charts

https://gatsby-twitter-github-charts.vercel.app

From / By https://github.com/LekoArts

https://github.com/LekoArts/lekoarts-stats

https://lekoartsstats.gatsbyjs.io/

## Environment variables:

```java
const core = require('@actions/core')
const axios = require('axios')
const AWSAppSyncClient = require('aws-appsync').default
const { GITHUB_QUERY, createGithub, createTwitter } = require('./graphql')

const GITHUB_GRAPHQL_API = 'https://api.github.com/graphql'
const TWITTER_API = process.env.TWITTER_API
const AWS_GRAPHQL_API = process.env.AWS_GRAPHQL_API
const AWS_TOKEN = process.env.AWS_TOKEN
const AWS_REGION = process.env.AWS_REGION
const GITHUB_TOKEN = process.env.GITHUB_TOKEN
```

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/gatsby-twitter-github-charts.git
git push -u origin main
```

## GraphQL

```java
const client = createClient({
  url: process.env.AWS_GRAPHQL_API_URL,
  requestPolicy: 'network-only',
  fetchOptions: () => ({
    headers: {
      'Content-Type': 'application/graphql',
      'x-api-key': process.env.AWS_GRAPHQL_API_TOKEN,
    },
  }),
})

const QUERY =
query {
  listTwitters {
    items {
      id
      datetime
      followers
      tweets
    }
  }
  listGithubs {
    items {
      id
      datetime
      repos {
        id
        name
        url
        stars
        forks
      }
    }
  }
}


```

# LekoArts Statistics

Overview of my stats on GitHub and Twitter.

Pulled from the GitHub API and my internal Twitter Scraper. Uploaded to AWS Appsync.

Dashboard built with Gatsby.
