# All News Project

## Introduction

All news project is a service application which communicates
with browser extension that allows the user to read non-objective
news from several news channels. The extension
will identify which news article the user has read and suggests
more reading content about the same subject, In addition, the
application will give the user a summary on a specific subject
from a range of news websites,and in this way we give the user
the ability to read different-agenda news.

## Methods

When the user is reading a news article, the extension will
check if it is one of the news websites that is supported by the
system. if it is it will communicate with the cloud server rest API
that will check if there are any other news articles on the same
subject, then the extension will notify the user and suggest
that he also reads from other websites and offers more services
like a non-objective summary of the article that is a combination
of all the news articles that have the same article in a
different agenda.
The main core of the All News project is the server which is
based on Linux & Docker that manages and runs a couple of
different service components that each have a different part of the main goal.

## System architecture (MVC)

![system_design_overview](https://raw.githubusercontent.com/all-news-project/.github/main/images/system_design_overview.png)

## Client-Server sequence overview

```mermaid
sequenceDiagram
    Client->>Rest API: Reading news whils using Extension
    loop Cluster searching
        Rest API->>Server: Check if article in classifed
        Server->>Rest API: Return cluster
    end
    Note left of Rest API: If None
    Rest API-->>Client: No articels found!
    Note left of Rest API: Else if classfied
    Rest API-->>Client: Suggest articles with same topic!
```

## Using the Extension

- [Installation](https://github.com/all-news-project/extension/wiki/Installation)
- [How to use the extension](https://github.com/all-news-project/extension/wiki/How-to-use-the-extension)
- [User interface overview](https://all-news-project.github.io/ui/)

## Be part of the open source system
- [How to add new website web scraper](https://github.com/all-news-project/server/wiki/How-to-add-Scraper)
- [How to add new nlp model](https://github.com/all-news-project/server/wiki/How-to-add-NLP-model)
- [How create new database](https://github.com/all-news-project/server_utils/wiki/How-to-add-a-new-Database)
- [How to  configure MongoDB to the system](https://github.com/all-news-project/server_utils/wiki/How-to-configure-MongoDB-to-the-system)

## Extra
- [How the scraping tasks work?](https://github.com/all-news-project/server/blob/main/scrapers/web_scraper/README.md)
