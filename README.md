# Threads Scraper: Keyword Search, Posts & Profiles · No Login

Get public data from Threads (Meta) as clean JSON: **keyword search results, profiles with followers and bio, the latest posts of each profile, and single posts with their replies.** Paste keywords, usernames or links.

**[Run it on Apify](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)**: no install, no login, free credit on a new Apify account.

## What you get

**For each post**
- Text, date (UTC), link and post code
- Likes, replies, reposts, quotes and shares
- Author: username, name, verified badge, picture
- Images and videos (direct URLs), links in the text, link preview
- Whether it is a reply, a quote or a repost
- Where it came from (`source`: the search keyword, profile or post link)

**For each profile**
- Username, name, exact follower count, bio, bio links, verified, private, profile picture

## Pricing

**No login, no cookies, no account at risk. You pay only for what is delivered: $0.002 per post or profile.** Usernames that don't exist and invalid inputs are listed with the reason and never charged.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~threads-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"searchQueries": ["running shoes"], "profiles": ["zuck"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/threads-scraper").call(run_input={"searchQueries": ["running shoes"], "profiles": ["zuck"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add threads "https://mcp.apify.com?tools=pomlabs/threads-scraper" -t http
```

## Ready-made examples

- [Search Threads posts by keyword](https://apify.com/pomlabs/threads-scraper/examples/search-threads-posts-by-keyword)
- [Export a Threads profile and its posts](https://apify.com/pomlabs/threads-scraper/examples/export-threads-profile-posts)
- [Monitor a brand on Threads without an account](https://apify.com/pomlabs/threads-scraper/examples/threads-search-without-account)

## More Actors by Pom Labs

- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [AI Brand Visibility Tracker - ChatGPT, Claude & Perplexity](https://apify.com/pomlabs/ai-brand-visibility?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Mercado Livre & Amazon BR Coupon Code Checker](https://apify.com/pomlabs/mercadolivre-coupon-checker?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [NSFW Image Detector & Image Tagger - Moderation + Categories](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)
- [Google Trends Scraper: Related Queries, No 429 · $2/1K](https://apify.com/pomlabs/google-trends-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper)

Full documentation, input fields and output format: [Threads Scraper: Keyword Search, Posts & Profiles · No Login on Apify](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=threads-scraper).
