# Intermediate MPI Programming

This section covers some more advanced aspects of MPI including non-blocking communcations (universally used to avoid deadlock), collective communication patterns, virtual topologies and derived datatypes. The relevant exercises are numbers 5, 6, 7 and 8; exercise 9 is entirely optional, but hopefully fun to attempt.
This block also includes simple example solutions to the basic exercises.


---

## Learning Objectives

After completing this section the student will:
- gain familiarity with intermediate aspects of MPI such as non-blocking and collective communication, virtual topologies and derived datatypes
- have gained practical experience by solving various exercises

---

## Non-Blocking Communication

This subsection covers non-blocking communication functions (e.g. _MPI\_Isend_ and _MPI\_Irecv_) that can be used to avoid deadlock ([slides](../slides/L07-nonblocking.pdf)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_5zcjtmqn?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_5zcjtmqn&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_k47i55sd#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_wnzkxqhw?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_wnzkxqhw&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_2tw5nhzu#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_iimhk58i?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_iimhk58i&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_azdo74gf#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_fqhhs3d8?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_fqhhs3d8&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_xj06z6j7#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

## Collectives

This section covers collective communication patterns such as _MPI\_Barrier_, _MPI\_Bcast_, _MPI\_Scatter_, _MPI\_Gather_, _MPI\_Scan_, _MPI\_Reduce_ and _MPI\_Allreduce_ ([slides](../slides/L08-collective.pdf)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_yjvocn09?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_yjvocn09&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_4lk7s2aq#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_q2bylm8h?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_q2bylm8h&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_52wgxb0x#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

## Virtual Topologies

This subsection covers creation and use of virtual topologies in MPI to simplify structured communication ([slides](../slides/L09-topology.pdf)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_ko3q9wma?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_ko3q9wma&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_qiguy4k0#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_x624o5sa?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_x624o5sa&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_uuyrqwn2#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_j0wl7v8m?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_j0wl7v8m&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_ftai79tr#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

---

## Derived Datatypes

This subsection covers derive datatypes, which facilitate communication of composite data structures and non-contiguous data ([slides](../slides/L10-derivedtypes.pdf)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_rr91ywta?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_rr91ywta&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_102mr9l9#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

 ```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_otnlt47w?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_otnlt47w&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_vfwf8tje#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_jctjoyxo?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_jctjoyxo&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_jct35wa8#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_k07ud1ly?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_k07ud1ly&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_m5sjdg12#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Simple example solutions using MPI in C and Fortran can be downloaded [here](../exercises/MPP-solutions.tar).
