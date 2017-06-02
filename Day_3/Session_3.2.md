# Day 3, Session 2
### 10:45 am – 12:00 pm
## Scraping a podcast feed

- Talking Machines podcast
- [http://www.thetalkingmachines.com/ways-to-listen](http://www.thetalkingmachines.com/ways-to-listen)

```
wget http://www.thetalkingmachines.com/blog/?format=RSS -O feed.xml
```

```bash
grep ".mp3" feed.xml > url_lines.txt
```

Work on building labeler for the rest of the day


<!-- Output can be overlay in SV or a list of separate files -->

