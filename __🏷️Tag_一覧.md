
```dataview
TABLE without id tags,rows.file.link FLATTEN tags 
WHERE tags != null AND length(tags) > 0
GROUP BY tags
```
