# Katameros

## An API for the daily Coptic readings of the Coptic Orthodox Church.

[Toutbabahator.com](https://toutbabahator.com/) is a Liturgical Framework that Coptic Orthodox Church Organizations can use to embed religious content into their website or apps. This framework utilizes Amazon Web Services EC2 Virtual Server.

The json files were generated using a bash script to scrape content from already existing live web content.

To make use of the resources on this server, you have a number of options described below:
  1. Make use of the URLs http://toutbabahator.com/synaxar.htm or http://toutbabahator.com/readings.htm for embedding the day's Synaxarium and/or Readings onto your website
  2. Make use of the URL http://toutbabahator.com/display.php for embedding onto your website or for casual browsing from your computer or mobile device. Apps are on their way to accomodate this aspect as well.
  3. Make use of the URLs http://toutbabahator.com/toutbabahator.php?choice=synaxar and/or http://toutbabahator.com/toutbabahator.php?choice=readings to get a direct JSON feed for each day's Synaxarium or Readings
  
### Synaxarium - JSON Structure
The JSON feeds for the daily Synaxarium are organized as an array (one per JSON file) with each element containing the following items:
  1. One synaxartitle
  2. One synaxareading

Note: the first element is the Coptic Month and Day. 
```
  [{
    "synaxartitle":"Tuba","synaxareading":"1"
  },
  {
    "synaxartitle":"The Departure of Anba Kyrellos (Cyril) the...","synaxareading":"On this day of the year..."
  },
  {
    "synaxartitle":"The Martyrdom of the Saints...","synaxareading":"On this day also the Saints..."
  }]
```

### Readings - JSON Structure
The JSON feeds for the daily readings are organized as an array (one per JSON file) with each element containing the following items:
  1. The reading "Type" (Vespers, Matins or Liturgy)
  2. The "PaulineEpistle" - will be null for types other than Liturgy
  3. The "CatholicEpistle" - will be null for types other than Liturgy
  4. The "Acts" of the Apostles - will be null for types other than Liturgy
  5. The "Psalm" Reading(s) - will be null for types other than Liturgy
  6. The "Prophecy" Reading(s) - appears under Matins during the Lenton season
  7. The "Gospel" Reading - appears under all three types (Vespers, Matins and Liturgy)
  
  Again, the first element is the Coptic Month and Day.
  ```
  [{
    "Type": "Baramhat 14",
    "PaulineEpistle": "Null",
    "CatholicEpistle": "Null",
    "Acts": "Null",
    "Psalm": "Null",
    "Prophecy": "Null",
    "Gospel": "Null"
  },
  {
    "Type":"Vespers",
    "PaulineEpistle":"Null",
    "CatholicEpistle":"Null",
    "Acts":"Null",
    "Psalm":"Psalm 34:7-8 The angel of the LORD encamps all around those who...",
    "Prophecy":"Null",
    "Gospel":"Matthew 16:24-28 Then Jesus said to His disciples, \"If anyone..."
  },
  {
    "Type": "Matins",
    "PaulineEpistle": "Null",
    "CatholicEpistle": "Null",
    "Acts": "Null",
    "Psalm": "Null",
    "Prophecy": "Exodus 4:19-end ; Exodus 6:1-13 ; Joal 2:21-26 ; Isaiah 9:9-end ; Isaiah 10:1-4 ; Job 12:1-end ; Job 13:1-end ; Job 14:1-22 Exodus 4:19-end ; Exodus 6:1-13 RETURN RETURN Now the LORD said to Moses in Midian, \"Go, return to Egypt; for all the men who sought your life are..."
  },
  {
    "Type": "Liturgy",
    "PaulineEpistle": "2nd Thessalonians 2:9-17 The coming of the lawless one is according to the working of...",
    "Psalm": " 27:7-8 Hear, O LORD, when I cry with my voice! RETURN Have mercy also upon me, and...",
    "Prophecy": "Null",
    "Gospel": "Luke 4:1-13 Then Jesus, being filled with the Holy Spirit, returned from the Jordan and was led by..."
  }]
  ```
  
  ### Credits
I found this wonderful piece of work hidden deep in the corners of the internet; posted in a [random discussion on tasbeha.org](https://tasbeha.org/community/discussion/16760/project-request-open-source-lectionary) by the user elipti. 

I've posted it here on GitHub so that developers can find it.

I have no idea who Elipti is, their whereabouts or who they are. But it is safe to say, this individual, is carrying the whole of the digital Coptic Church solely on their shoulders. 

May God shower them with grace 💫 🙏.
