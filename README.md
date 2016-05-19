# kexp
Nicely display all the KEXP live performances.

## References

All live performances per year like this:
- https://www.kexp.org/live/default.aspx?month=0&year=2015
- https://www.kexp.org/live/default.aspx?month=0&year=2014

See the latest few with date like this:
- https://www.kexp.org/live/

Official feed:
- http://feeds.kexp.org/kexp/liveperformances

Official KEXP Youtube feed:
- https://www.youtube.com/user/kexpradio/videos
- https://www.youtube.com/feeds/videos.xml?user=kexpradio

Youtube API Stuff:
- http://stackoverflow.com/questions/18953499/youtube-api-to-fetch-all-videos-on-a-channel
- http://stackoverflow.com/questions/6331053/how-can-i-get-all-videos-ids-from-a-youtube-channel

Work with the Google API explorer!
- https://developers.google.com/apis-explorer/#p/youtube/v3/

Get channel id of radio KEXP:
```
GET https://www.googleapis.com/youtube/v3/channels?part=id&forUsername=kexpradio&key={YOUR_API_KEY}
```

Get videos of radio KEXP:
https://developers.google.com/youtube/v3/docs/search/list
```
GET https://www.googleapis.com/youtube/v3/search?order=date&part=id%2C+snippet&q=full&channelId=UC3I2GFN_F8WudD_2jUZbojA&maxResults=50&key={YOUR_API_KEY}
```
Then work with the `nextPageToken` to get more results.
Total of videos can be found in the pageInfo->totalResults variable.

But beware of Google API quotas!
https://developers.google.com/youtube/v3/getting-started#quota

## automatic python magic
- get all videos from channel with [youtubeChannelVideosFinder](https://github.com/dsebastien/youtubeChannelVideosFinder) or [manually](https://stackoverflow.com/questions/18804904/retrieve-all-videos-from-youtube-playlist-using-youtube-v3-api)
- download them all with [pafy](https://github.com/mps-youtube/pafy)
