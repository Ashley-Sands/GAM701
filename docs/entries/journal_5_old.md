## Punk 
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

In the first lecture this week we where asked to start thinking about ideas releating to culture and society. Furthermore, we had to also think of some technical asspects or aesthetics that we would like to work on. The next day in the workshop we where asked to complile our ideas into a Mural board shared among the cohort, which we would then become a market place of ideas. We then had to choose some of the ideas we liked and form teams to begin producing a game artifact.My Mural board consisted of meny idea based around conspiracy theories, religon, 90s and cororation for the cultureal aspect; real-time audio synthesis, flocking (AI) for technical and old school comic books as an aesthetic [fig. 1]. 

[fig. 1][Mural board]

Looking back i may of missed the point a little, as most people just focused on developing a single idea around a cultural and technical/aesthetic aspect, however i had few randome ideas. The first was to was to re-imagin how physics would work on a flat earth in a sola system based around our current understanding. You would then have to protect the flat earth form extraterrestrials and UFOs. The second idea was to have a island with a road network and serval cities, the player would have to place work and events around island conntected to roads witch the citazens would have to travle to. The player would have to serticly place the work and event locations around to prevent grid lock, which would become gameover.

However, most other ideas in the cohort where much more delveloped than mine, therefor i joined another group. Which to be honest had quite a good idea in my opinion. 

### Sub-Heading

This is a template for journal entries to help keep consistency!  
[Page content goes here]

<br />

### Cites
##### All citations are available in a single [bibtex file](../references.bib)

<p id="c1">
[1] Author, “Title,” [Online]. Available: URL, [Accessed: day Month Year] 
</p>

<br />
<br />

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

<br />
<br />

**Please refer to the [Licences and Sources](../resources/licences-and-sources) document for content used from external sources along with usage and licence infomation**

<br />

<script>
// Store the entry id and published values in a JS script, to make life easier with updateing links.
entry_id  = 5
published = "13-10-2021" 
week = 4

document.getElementById("index").innerHTML = entry_id
document.getElementById("published").innerHTML   = `${published} (Week: ${week})`


next_page = "journal_"+ (entry_id + 1)
priv_page = "journal_"+ (entry_id - 1)

next_links = document.getElementsByClassName("next_entry")
priv_links = document.getElementsByClassName("priv_entry")

// atempt to fetch the next page. 
// if we get an ok responce display the next links, 
// otherwise we have most likely reaced the end.
fetch('./'+next_page+'.html')
    .then (
        responce => {
        if ( responce.ok ) 
            for ( let i in next_links )
                next_links[i].innerHTML = '<a href="./'+next_page+'">Next ></a>'
        }
    )

// only display the priv page link if we have gone past the first page.
// theres no need to fetch the prv page, since we know the min id is 0
if (entry_id > 0)
    for ( let i in priv_links )
        priv_links[i].innerHTML = '<a href="./'+priv_page+'">< Priv</a>'


</script>