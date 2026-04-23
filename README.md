# Google Reverse Image Search

I wanted reverse image search I could call from code: to verify where an image originated, find higher-res versions, cross-check provenance. Google's search-by-image only works through the UI, there's no official API. So I scraped the endpoint and wrapped it behind a single `response()` call.

Python wrapper for Google's reverse image search.

## Install

```bash
git clone https://github.com/ramonclaudio/Google-Reverse-Image-Search.git
cd Google-Reverse-Image-Search
pip install -r requirements.txt
```

## Usage

```python
from reverse_image_search import GoogleReverseImageSearch

r = GoogleReverseImageSearch()
print(r.response(
    query="Example Query",
    image_url="https://example.com/image.jpg",
    max_results=5,
))
```

## Rate limiting

`response()` accepts an optional `delay` parameter (seconds) to space out subsequent page requests. Applies only after the first request. Defaults to 1 second.

```python
r.response(
    query="Example Query",
    image_url="https://example.com/image.jpg",
    max_results=10,
    delay=5,
)
```

## License

MIT
