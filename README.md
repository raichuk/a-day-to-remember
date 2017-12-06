# A Day to remember

## Description

`a-day-to-remember` is an experiment involving the serverless architecture of Auth0 webtasks and
taking advantage of [IFTTT](https://ifttt.com)  built in services, specifically Telegram bots.

## Endpoints example
## Base URL
```sh
https://wt-2d0c1b127ddf2114db57608a0d9ef965-0.run.webtask.io/a-day-to-remember/?webtask_no_cache=1
```

### Add item
```sh
$ curl -s "https://wt-2d0c1b127ddf2114db57608a0d9ef965-0.run.webtask.io/a-day-to-remember/?webtask_no_cache=1&op=add&item=water"
{"ok":true,"msg":"Item added"}
```
Adds the item to a mongolab db.

#### Parameters
- op: add
- item: item's name
 

### Get all items (it returns text/html so I recommend using browser)
```sh
$ curl -s "https://wt-2d0c1b127ddf2114db57608a0d9ef965-0.run.webtask.io/a-day-to-remember/?webtask_no_cache=1&op=get"
<ul><li>oil</li><li>meat</li><li>onions</li><li>2 gallons of water</li><li>garlic</li><li>pepsi</li><li>olive-oil</li><li>oliveoil</li><li>olives</li><li>crackers</li><li>chicken</li><li>butter</li><li>eggs</li><li>bread</li><li>water</li></ul>
```
Gets all the items that were added.

#### Parameters
 - op: get
  
## IFTTT Applets

Two applets were added to my IFTTT account.

### Add applet
Interacts with ifttt telegram bot, every time y type:
```
buy something
```

It will trigger the add item endpoint, adding the item to the list

### Remind applet
Near the time I left my job it me sends an url  the grocery list I built with the previous commands.
Triggering the get all endpoint and showing on browser.
