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

- Empathy....
  - Talk about the games in the paper and how we could of importerated aspect of them into our game.
  - and relate this to how we mabe missed the main gole pf the project.

-->
The theam for this weeks workshops is rapid ideation methods, which will become the basis for creating a prototype for a text driven game; which is theamed around 'Call and Responce'. Furthermore, there should be much consideration for the role of empathy and moral agency and while the game should be text-driven, it doent limit us to text-base adventures. But rather opens the posiblities to visule novals through to open 2D/3D worlds and even includes paper protypes. It has been breifed that the player should be able to atain the resolution within 5 minutes of game play.  

For this project we where put into teams of three or four people and begain discussing ideas. We decided to focus on mental health and decided to use a nutral and relatable character who is strugging to deal with several emotions. When a negative emotion is experances, we enter the mind of our protagonist and play out the strugles, to only relise that everthing will be ok in the end.

For the emotions we decided to focus on lonliness, frustration and boardom which are all set in different location, each with there own unquniue character that we feel reresents the emotion. For loneliness we decided to use a scropion lost in the desert tring to find thire frends and family; for frustration we whent for a salamander tring to find a calming scatory on the face of a volcaion; and lastly for boardom, you play as a sloth who has to climb the tallest tree to conqure the unhappiness. To illastrate our world we decided to go for a 2d pixial art top-down adventure, simulare to the old school Lengend of Zelder and pokemon games.

[Image-Pokimon][Fig. 3] [Image-Zelder][Fig. 4]

However, somwhere along the lines we lost (or forgot) the emotianl dialogue aspect and overlooked how we where actully going to induce emperpohy on the player. In a later workshop at universtity each team was give a pice of writing to ready and we where given 'Designing Game to Foster Empathy' [[1](#c1)] witch was really fitting since it somthink that we lost during the designe process of our project. The paper has an incredably insighfull litture review of different forms of empathy taken from many areas of research. Furthermore, it gives a number of sugestions and pricials for incorperating empathy into games and rounds of the paper by giving some example 'games for good'. So lets a take a dive into the paper and have a look at how we could of add empathy into our game. 

The litriture review begins with explain that empathy is an important area of research, which has been investergated in a wind rage of fields for conflict resolution and psycholgy to helath care traning and even pre-school education. However, in social science it can be described as two broad categories of empathy[Stephan & Finlay, 1999]. The first 'cognituve empathy' which refers to intentionally taking anothers person' point of view. While on the other hand, 'emotional empathy' can be divided into two sub catagories, parallel and reactive. Parallel empathy is understanding vicarious experience of another emotional state. While reactive is described as an emotional response that is dissimilar to what the other person is experancing [Stephan and Finlay (1999)]. 

The paper then follows up with a wealth of information regarding these two board areas of research, however, its abit beond the scope of this artical. Therefor, we'll now begin to look at some of the sugestions and pricebals sugested in Belman and Flanagn's artical. Also befor we continue, the authors make a point that these are an evolving set of principles rather than a comprehensive set of guidlines.

1) *Players are more likly to empathise when an intentional effort is made when the game begins. This can be approched explicitly or via a more subtle encouagement focusing on an empathrtic posture. However, if empathetic induction is inefective from the offset, most players will play "unempathetically".*

This pricable reminds me of the opening scene of 'Ori and The Blind forest' ........




we where given a an acerdemic journal or blog post to read,  

When our protagonist experances one of thire negative emotions

When we where first put into our teams, one of our members (Daz) came up with a fairly stong idea that would become base to our project. The idea consisted of portraying several emotions in regards to a mental health situation, which we then starting further develop. My first thourth was that we should set it during the covid lock-down, since it could be a relatable situation for meny people. We then started to disscuse how we could turn this idea into a playable game and decided that it should be 2D. Megan (another team member) mentioned making it a side-scroller, simular to the old skl mario games [fig. 1][fig. 2]. Thinking of the more old skl games trigger me suggest maybe approching it from an top-down perspective in the style of the original Pokimon [fig. 3] and Zelder games [Fig. 4]. The other two in the team, aggreed to take an old school top-down approch since it would give them the opertunity to try there hand at some pixle art, which is somthink that nither had done within there art profession. 

[Image-Mario][Fig. 1] [Image-Mario][Fig. 2]
[Image-Pokimon][Fig. 3] [Image-Zelder][Fig. 4]

Now we had a rought idea for theame of the story and style of the game, we decided 

<!--
I think i should take another approch to this. as it not coming to mind correctly. (Also just skip this date)

I think i should disscues empathy and me. 

-->

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
published = "05-10-21" 
week = 3

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