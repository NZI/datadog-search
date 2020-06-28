# Datadog Search

This bookmarklet adds a quick way to get straight from your current page to the last hour Datadog search

```
  var loc = window.location.pathname;
  if (loc = prompt("Enter URL to search on Datadog", loc)) {
    var from_ts = (+ new Date()) - 3600000;
    var to_ts = (+ new Date());
    var search = encodeURIComponent(loc.replace(/\//g, '\\/'));
    var url = "https://app.datadoghq.com/logs?cols=%40app.tenant%2C%40http.status_code&event&from_ts="+from_ts+"&index=&live=true&messageDisplay=inline&query="+search+"+-status%3Ainfo&stream_sort=desc&to_ts="+to_ts;
    window.open(url, '_blank')
  }
```

To make this available everywhere, add the following as the URL in a bookmark:

```
javascript:(function(){
  var loc = window.location.pathname;
  if (loc = prompt("Enter URL to search on Datadog", loc)) {
    var from_ts = (+ new Date()) - 3600000;
    var to_ts = (+ new Date());
    var search = encodeURIComponent(loc.replace(/\//g, '\\/'));
    var url = "https://app.datadoghq.com/logs?cols=%40app.tenant%2C%40http.status_code&event&from_ts="+from_ts+"&index=&live=true&messageDisplay=inline&query="+search+"+-status%3Ainfo&stream_sort=desc&to_ts="+to_ts;
    window.open(url, '_blank')
  }
})()
```
