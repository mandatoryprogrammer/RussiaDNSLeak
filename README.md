![](https://i.imgur.com/6oyUJH0.jpg)

# Russian DNS Leak (All .ru, .su, .tatar, .рф, and .дети Domains) 

## Summary
Due to an accidentally enabling of [global zone transfers](https://en.wikipedia.org/wiki/DNS_zone_transfer) on the Russian DNS nameservers `a.dns.ripn.net`, `d.dns.ripn.net`, and `f.dns.ripn.net` the [TLDR project](https://github.com/mandatoryprogrammer/TLDR) was able to capture a complete list of all domains registered under Russian TLD space. Russia has fixed this issue (possibly due to the problem [gaining traction after the TLDR project link was  posted to a Russian tech news aggregator](https://habrahabr.ru/post/331144/) by [@ValdikSS](https://twitter.com/ValdikSS)) so I am creating this repository to summarize the data collected due to this leak. Humorously the leak actually caused an outage for this TLDR service because the [leaked zone data was so large it killed the script attempting to collect it by filling up all available memory on the server](https://github.com/mandatoryprogrammer/TLDR/issues/11#issuecomment-309254675). This issue has now been fixed and the leaked DNS data is all backed up and hosted here for general consumption. The size of this dump is enormous compared to previous leaks such as the previously captured [North Korean DNS dump](https://github.com/mandatoryprogrammer/NorthKoreaDNSLeak), `.ru` domains alone account for over *[5.1% of all domain names on the Internet](https://w3techs.com/technologies/overview/top_level_domain/all)*.

### Number of Domain Names Leaked
* `.ru (Russia ccTLD)`: 5,214,868 domains.
* `.su (Soviet Union ccTLD)`: 104,591 domains.
* `.tatar ( gTLD)`: 861 domains.
* `.рф ( IDN ccTLD)`: 466,890 domains.
* `.дети ( gTLD)`: 821 domains.

Total domains: 5,788,031

### Downloads of Leaked Zone Data
* `.ru` Zone data: [Download here](https://github.com/mandatoryprogrammer/TLDR/blob/e04bef94efbf546760888b7608fee10e6639aede/archives/ru/a.dns.ripn.net.zone.gz?raw=true) (Compressed due to large size)
* `.su` Zone data: [Download here](https://raw.githubusercontent.com/mandatoryprogrammer/TLDR/e04bef94efbf546760888b7608fee10e6639aede/archives/su/a.dns.ripn.net.zone)
* `.tatar` Zone data: [Download here](https://raw.githubusercontent.com/mandatoryprogrammer/TLDR/e04bef94efbf546760888b7608fee10e6639aede/archives/tatar/a.dns.ripn.net.zone)
* `.рф` Zone data: [Download here](https://github.com/mandatoryprogrammer/TLDR/blob/e04bef94efbf546760888b7608fee10e6639aede/archives/xn--p1ai/a.dns.ripn.net.zone.gz?raw=true)
* `.дети` Zone data: [Download here](https://raw.githubusercontent.com/mandatoryprogrammer/TLDR/e04bef94efbf546760888b7608fee10e6639aede/archives/xn--d1acj3b/a.dns.ripn.net.zone)

Additionally this repository can be cloned in order to obtain a copy of all of these zone files.

### General Nerdiness
As a fun aside, it would appear that some nerds were planning on people viewing the zone data in its entirety (possibly the zone operators?) and have registered 23 domains in alphabetic order to make the following ASCII art picture in the beginning lines of the `.ru` zone data:

```bind
0--0------A1--------------------------------------------------1.RU. 345600 IN NS ns-de.bible.ru.
0--0------A1--------------------------------------------------1.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A1--------------------------------------------------1.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A2--BBBBB--I-BBBBB--L------EEEEEE-----RRRRR--U----U-2.RU. 345600 IN NS ns-de.bible.ru.
0--0------A2--BBBBB--I-BBBBB--L------EEEEEE-----RRRRR--U----U-2.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A2--BBBBB--I-BBBBB--L------EEEEEE-----RRRRR--U----U-2.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A3--B----B-I-B----B-L------E----------R----R-U----U-3.RU. 345600 IN NS ns-de.bible.ru.
0--0------A3--B----B-I-B----B-L------E----------R----R-U----U-3.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A3--B----B-I-B----B-L------E----------R----R-U----U-3.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A4--BBBBB--I-BBBBB--L------EEEEE------R----R-U----U-4.RU. 345600 IN NS ns-de.bible.ru.
0--0------A4--BBBBB--I-BBBBB--L------EEEEE------R----R-U----U-4.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A4--BBBBB--I-BBBBB--L------EEEEE------R----R-U----U-4.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A5--B----B-I-B----B-L------E----------RRRRR--U----U-5.RU. 345600 IN NS ns-de.bible.ru.
0--0------A5--B----B-I-B----B-L------E----------RRRRR--U----U-5.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A5--B----B-I-B----B-L------E----------RRRRR--U----U-5.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A6--B----B-I-B----B-L------E----------R---R--U----U-6.RU. 345600 IN NS ns-de.bible.ru.
0--0------A6--B----B-I-B----B-L------E----------R---R--U----U-6.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A6--B----B-I-B----B-L------E----------R---R--U----U-6.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A7--BBBBB--I-BBBBB--LLLLLL-EEEEEE--0--R----R--UUUU--7.RU. 345600 IN NS ns-de.bible.ru.
0--0------A7--BBBBB--I-BBBBB--LLLLLL-EEEEEE--0--R----R--UUUU--7.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A7--BBBBB--I-BBBBB--LLLLLL-EEEEEE--0--R----R--UUUU--7.RU. 345600 IN NS ns-ru.bible.ru.
0--0------A8--------------------------------------------------8.RU. 345600 IN NS ns-de.bible.ru.
0--0------A8--------------------------------------------------8.RU. 345600 IN NS ns-nl.bible.ru.
0--0------A8--------------------------------------------------8.RU. 345600 IN NS ns-ru.bible.ru.
```

Clever work folks, possibly the most obscure graffiti out there :)