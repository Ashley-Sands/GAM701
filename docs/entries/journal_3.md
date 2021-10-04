## Rapid Ideation Methods and Prototyping
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

<!-- Points to write about.
- lack of leardership
- unorganised
- No GDD, lack of kamban board
- Lost sight of main goal.
  - narrative
  - protray emotion
- bringing it all together.
- WS - Not paying enought attenct to the Nural board.
  - and not doing the activatie assigned.
  - 

##
Title:  rapid ideation/prototype??
##

- This has made relise that i need to pay a bit more attachen
- Rapid Ideation and Prototypeing methods.


-->
The theam for this weeks workshops is rapid ideation methods, which will become the basis for creating a prototype for a text driven game; which is theamed around 'Call and Responce'. Furthermore, there should be much consideration for the role of empathy and moral agency and while the game should be text-driven, it doent limit us to text-base adventures. But rather opens the posiblities to visule novals through to open 2D/3D worlds and even includes paper protypes. It has been breifed that the player should be able to atain the resolution within 5 minutes of game play.  

When we where first put into our teams, one of our members (Daz) came up with a fairly stong idea that would become base to our project. The idea consisted of portraying several emotions in regards to a mental health situation, which we then starting further develop. My first thourth was that we should set it during the covid lock-down, since it could be a relatable situation for meny people. We then started to disscuse how we could turn this idea into a playable game and decided that it should be 2D. Megan (another team member) mentioned making it a side-scroller, simular to the old skl mario games [fig. 1][fig. 2]. Thinking of the more old skl games trigger me suggest maybe approching it from an top-down perspective in the style of the original Pokimon [fig. 3] and Zelder games [Fig. 4]. The other two in the team, aggreed to take an old school top-down approch since it would give them the opertunity to try there hand at some pixle art, which is somthink that nither had done within there art profession. 

[Image-Mario][Fig. 1] [Image-Mario][Fig. 2]
[Image-Pokimon][Fig. 3] [Image-Zelder][Fig. 4]

Now we had a rought idea for theame of the story and style of the game, we decided 

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

<script>
// Store the entry id and published values in a JS script, to make life easier with updateing links.
entry_id  = 3
published = "01-10-21" 
week = 2

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