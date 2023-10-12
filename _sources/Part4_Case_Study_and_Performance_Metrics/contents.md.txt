# Case Study and Performance Metrics

This section provies various tips and tricks for MPI programming along with a case study and discusses performance analysis that can be used to assess the scalability and efficiency of your applications.


---

## Learning Objectives

After completing this section the student will have:
- discussed various issues wrt correctness, portability, maintainability and performance of MPI programs
- familiarity with analysing the performance of their applications
- gained additional experience using a larger case study

---

## Tips and Tricks
 
This subsection covers various aspects of MPI programming that will help write correct, portable, maintainable and efficient programs ([slides](../slides/L12-tipsandtricks.pdf)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_pvw9x9st?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_pvw9x9st&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_hmx3p6k7#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_gna7jj9s?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_gna7jj9s&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_49y5zw70#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_7xskoqfl?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_7xskoqfl&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_zxztkoik#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


---

## Image Processing Case Study

The following video describes the image processing case study ([slides](../slides/L11-casestudy.pdf)).

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_gr97hjxg?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_gr97hjxg&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_iyzqpln8#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```

Case study materials: 
-  [exercise description](../exercises/MPP-casestudy.pdf)
-  [baseline code including helper functions](../exercises/MPP-casestudy.tar)
-  [example solution](../exercises/MPP-casesolns.tar)
-  [example of using arralloc function](../exercises/MPP-arralloc.tar)

It is recommended to first attempt to write your own serial and parallel solutions and then compare to the solutions provided. Note that Fortran supports dynamic array allocation as a language feature.

---

## Performance Metrics

Performance and scalability are important to assess because a code that scales poorly won't be using larger machines efficiently.

This subsection covers performance metrics (Speedup, Efficiency), strong and weak scaling, and also discusses Amdahl's Law and Gustafson's Law and how to visualise performance results ([slides](../slides/L13-scaling.pdf)).


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_7r1s2lbn?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_7r1s2lbn&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_ta1rgk0o#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_o3an3197?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_o3an3197&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_2w4fylpg#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_cnep5k1d?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_cnep5k1d&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_spipf0h2#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>

```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_hlf3odh7?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_hlf3odh7&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[mediaProxy.mediaPlayFrom]=0&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_81x9p5sh#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_medxuqap?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_medxuqap&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_0cp0q5ab#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```


Congratulations! 

You have completed this MPI programming course!


Please take a moment to complete the [post-course questionnaire](https://forms.office.com/r/aUth2aKHvD) and provide us some [feedback](https://www.archer2.ac.uk/training/feedback/?course=210000-mpi-self-service) to help improve this course. Note that the feedback form is designed to be anonymous, although you can leave your contact details if you wish. We use the same form for all training courses, so some questions (e.g. regarding the venue) may not be relevant. Thank you!

