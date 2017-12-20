# twitter-web-scraping

## Program Function
This is a web-scraping program to retrieve tweets (filtered by date and geography) from Twitter.

Twitter doesn't provide a API to help developer to get tweets filtered both by history dates (a week before) and geography. 

But Twitter provide search techniques like this:
![](https://ws2.sinaimg.cn/large/006tNc79gy1fmo0as8gw7j31kw0iddhm.jpg)

The objective of this program is to build HTTP requests and simulate user actions like scrolling down to get all tweets.

## Parameter setting

You should find the following snippet in the bottom of file.
You can change these parameters manually.
```python
if __name__ == '__main__':
    # search tweets posted in latitude = 40.730610, longitude = -73.935242, radius = 5 
    set_geo(40.730610, -73.935242, 5)
    # search tweets posted between 2016-5-29 and 2016-5-31
    set_date(2016, 5, 29, 2016, 5, 31)
    # start scraping tweets
    start_scraping()
```
After execution, tweets will be grouped by date and stored in json files. 

## Results
like this:
```json
{"timestamp": "16:59 - 29 mag 2016", "timestamp_ms": "1464566370000", "fullname": "\nNorthern Bell", "username": "@NorthernBellNY", "content": "\nDuClaw Sour Me This now available on tap. http://brmn.us/1Is6JcT @duclawbrewing #BeerMenus\n"}
{"timestamp": "16:58 - 29 mag 2016", "timestamp_ms": "1464566327000", "fullname": "\nDon Valdez", "username": "@Don_Valdez", "content": "\nWedding tux. Shoutout to Jon for the reco- Thanks to Jeremy for the wonderful time! (at @EnzoCustom Clothiers)https://www.swarmapp.com/c/lEgUm7pOC3k\n"}
{"timestamp": "16:58 - 29 mag 2016", "timestamp_ms": "1464566289000", "fullname": "\njdorf", "username": "@jdorf", "content": "\ntonight's entertainment... @ The Public Theater https://www.instagram.com/p/BGAqvywszr-/\n"}
{"timestamp": "16:57 - 29 mag 2016", "timestamp_ms": "1464566234000", "fullname": "\nCory Bonfiglio", "username": "@CoryBonfiglio", "content": "\nDrinking a Frambuesa I Chocolate by @hoftendormaal at @beerstreetny http://untp.beer/s/c317578872\n"}
{"timestamp": "16:57 - 29 mag 2016", "timestamp_ms": "1464566231000", "fullname": "\nJohny ", "username": "@tranceboy_johny", "content": "\nI'm at Zenon Taverna in Astoria, NY https://www.swarmapp.com/c/84nsiZ1EcSK\n"}
```


## Cautions
If the number of tweets you scraping is relatively large, your ip will be blocked by Twitter, which means you can still use normal functions but advanced search techniques is impossible. Don't worry, block can be removed in a few days. My suggestion is to take turns to use proxies to build requests or connect a new WIFI after block.   
