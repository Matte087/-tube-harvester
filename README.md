
**tube-harvester**



An n8n workflow that automatically syncs YouTube channel data into a PostgreSQL database every night at midnight.
What it does
Fetches all videos and playlists from a YouTube channel via the YouTube Data API and upserts them into a PostgreSQL table (youtube_videos). Pagination is handled automatically — no duplicates, no manual intervention.
Requirements

n8n instance
YouTube Data API credentials (OAuth2)
PostgreSQL database

Setup

Import My_workflow_public.json into your n8n instance
Replace the following placeholders in the workflow:

YOUR_PLAYLIST_ID — your YouTube playlist ID
YOUR_CHANNEL_ID — your YouTube channel ID


Connect your YouTube OAuth2 credentials to the HTTP Request nodes
Connect your PostgreSQL credentials to the database nodes
Activate the workflow

Database
The workflow writes to a youtube_videos table with the following fields:
ColumnTypeidstring (PK)titlestringdescriptionstringpublished_atdatetimethumbnailstringcreated_atdatetime
