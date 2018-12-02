# INSEE Brut

Mirror site for INSEE data aimed to be exhaustive, faster and easier to browse.

## Overall architecture

The Scrapy spider will run nightly on [ScrapingHub](https://scrapinghub.com/). It should fetch all data from the insee.fr website.

Then, a python build script will recompile Mustache templates using the scraped data and publish it. This will run on [Netlify](https://www.netlify.com/).

## Deploy Scrapy spider to Scrapinghub

The first time, you need the shub dependency

```
pip3 install shub
shub login
```

And then each time you want to deploy :

```
cd scrapy-project
shub deploy 362041
```

## Local setup

```
mkvirtualenv insee-brut
workon insee-brut
pip3 install -f requirements.txt
```

To start a crawl :

```
cd scrapy-project
scrapy crawl insee
```
