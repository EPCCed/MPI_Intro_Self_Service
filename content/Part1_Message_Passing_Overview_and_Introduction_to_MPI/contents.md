# Introduction to the Message Passing Programming Model and MPI

In this section, we first cover message-passing at a conceptual level, and illustrate the basic concepts using a traffic-modelling thought experiment. We then introduce the very basics of MPI and how to develop real MPI programs on ARCHER2 or Cirrus. This is enough information to write simple "Hello World" programs in MPI, and get to grips with compiling and running your own parallel programs. This block also includes the main [MPI Exercise Sheet](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888441-dt-content-rid-20603993_1/xid-20603993_1) which we will use for the whole course, although only Exercise 1 is relevant here.


---

## Learning Objectives

After completing this section the student will gain:

- a thorough understanding of the Message Passing programming model
- familiarity with the core functions defined by Message Passing Interface (MPI) standard
- experience implementing, compiling, linking and running simple MPI programs

---

## Message Passing Programming Model

This section discusses the message passing programming model and introduces various communication patterns at conceptual level (see [slides](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888447-dt-content-rid-20603988_1/xid-20603988_1)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_c412efsc?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_c412efsc&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_yqbkuvyi#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_lflgoo4i?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_lflgoo4i&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_f5012d3k#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_fwdboeov?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_fwdboeov&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_scjqk5du#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_3n8m97ku?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_3n8m97ku&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_unhjgkup#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_6iertyie?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_6iertyie&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_0574knep#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

## Traffic Modelling

This subsection covers the traffic modelling thought exercise ([lecture slides](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888450-dt-content-rid-20603986_1/xid-20603986_1), [exercise](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888451-dt-content-rid-20603987_1/xid-20603987_1), [solution](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888454-dt-content-rid-20603994_1/xid-20603994_1)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_bi1jjb9w?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_bi1jjb9w&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_kv1mwzcv#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_vy3rtneb?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_vy3rtneb&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_bzzwlfw2#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_d487lmed?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_d487lmed&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_yb7yy8lb#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_3tye6090?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_3tye6090&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_j3qh2bgq#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---


## Introduction to MPI Programming


This subsection introduces MPI programming and several core functions ([slides](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888457-dt-content-rid-20603989_1/xid-20603989_1)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_ved6yzqa?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_ved6yzqa&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_qbqm7517#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/0_c21vap59?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=0_c21vap59&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_uqd00t6i#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Next videos cover running MPI programs on ARCHER2 and Cirrus ([slides](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888460-dt-content-rid-20798889_1/xid-20798889_1), [ARCHER2 notes](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888461-dt-content-rid-20625606_1/xid-20625606_1), [Cirrus notes](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888461-dt-content-rid-32451731_1/xid-32451731_1)) and the first exercise ([exercise slides](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888461-dt-content-rid-20603993_1/xid-20603993_1), [code archive](https://www.learn.ed.ac.uk/bbcswebdav/pid-5888461-dt-content-rid-20603992_1/xid-20603992_1)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_umfdoth2?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_umfdoth2&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_4tgdelpv#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_gbc2xd7q?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_gbc2xd7q&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_9veiwa9d#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

The next short video shows how to log on to ARCHER2, transfer files, and compile and run parallel programs.


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_slrvujkg?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_slrvujkg&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_lo305y3c#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

The following short video shows how to log on to Cirrus, transfer files, and compile and run parallel programs.


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_4vv745wp?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_4vv745wp&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_570vnzcb#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```
