import requests
import xml.etree.ElementTree as ET

def fetch_rss(url):
    response = requests.get(url)
    root = ET.fromstring(response.content)

    # RSS feeds often structure as: <rss><channel><item>...</item></channel></rss>
    items = root.find('channel').findall('item')

    print("\n📰 Top Headlines\n")
    for i, item in enumerate(items[:5]):
        title = item.find('title').text
        pub_date = item.find('pubDate').text
        link = item.find('link').text

        print(f"{i+1}. \"{title}\"\n   Published: {pub_date}\n   Link: {link}\n")

# Example usage:
fetch_rss('http://feeds.bbci.co.uk/news/rss.xml')
