# InnerTrends Cross Domain Tracking

Web apps that are hosted on a different domain than the website or the landing pages promoting the app require special attention for cross domain tracking, in order to not lose the information regarding the traffic sources that generated signups and payments.

Please follow these 2 steps in order to enable cross domain tracking:

1. Host the following file tsframe.html on the root of your website

Location: Website or Landing pages, when they are on a different domain than the application.


2. Add the following code to the web app source code

```
<script>
    var dataLayer = dataLayer||[];
    window.addEventListener('message', function (e) {
            dataLayer.push(JSON.parse(e.data))
    });
</script>

<iframe id="ifrm" src="https://www.website.domain/tsframe.html" with="1" height="1"></iframe>
```

**Important:** Replace www.website.domain with your website domain where you hosted the tsframe.html file.
