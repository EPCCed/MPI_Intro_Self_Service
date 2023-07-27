# Point-to-Point Communication

In this section we cover the basics of point-to-point message passing in MPI, and explain how the concepts of synchronous and asynchronous communication map to the specific MPI routines _Ssend_, _Bsend_ and _Send_. The exercises associated with this block are numbers 2, 3 and 4.

---

## Learning Objectives

By the end of the session the student will:
- gain familiarity with the functions required to send and receive messages
- understand the distinction between synchronous and asynchronous communication

---

## Point-to-Point Communication and MPI Functions

The next set of videos covers point-to-point communication (as cover by the [slides](../slides/L04-pt2pt.pdf))

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_r3qo1ntf?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_r3qo1ntf&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_ui6dvo31#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_7tm98a86?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_7tm98a86&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_if5kaoea#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_s08exp94?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_s08exp94&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_o3wwox4k#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_onzp1fgo?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_onzp1fgo&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_bd8tkrm3#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_21fahj8w?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_21fahj8w&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_95rddt04#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

## Pi Calculation Exercise

The following two videos discuss the solution for the Pi calculation exercise (see [code](../exercises/MPP-pi.tar)).

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_0wt3nzji?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_0wt3nzji&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_0ujfbiu4#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_ox1y00xg?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_ox1y00xg&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_ohc2j1zm#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

## Modes, Tags, Communicators

Finally, we cover modes, tags and communicators below (see [slides](../slides/L06-modetagcomm.pdf)).

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_24sro5n1?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_24sro5n1&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_i5nb5pm3#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_ppy90i4w?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_ppy90i4w&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_j4v38tj7#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```
