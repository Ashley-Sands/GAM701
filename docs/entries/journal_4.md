## The Importences of a Game Design Document
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

<!--
- In the privious project (Title goes here) we did a lack of project laning including a GDD and Scrum/Kamban board
- Talk about scrum and agile
- 
-->

In the [previous post](./journal_3) we had a look at how we could better induce empathy into our games. However, in the post we briefly mentioned that a few of our objectives were lost along the way, which on reflection was caused by poor project management. As a result, i think it would be beneficial to explore way to improve our project planning.

In the first day or so of the project we discussed our ideas as a team which gave us a rough concept for the artifact that we wanted to build. Furthermore, we discussed who was doing what and went our separate ways and cracked on, through a lot of things where forgotten. At no point during our discussions did we decide to put the plan on paper in the form of a game design document.

Once our discussion was over the very first thing, we should of done as a team, is create a short 1 to 2 page game design document. For a short project (or 'game jam') such as the one being undertaken, the document should be kept brief and not focused on the specifics. In the paper 'Simple Game Design Document Focused on Gameplay Features'[[1](#c1)], Danilo Márcio Lima de Carvalho et al describes some of key areas that should be included in the document for small indie and game jam projects.

Danilo Márcio Lima de Carvalho et al detail that there should be a general overview of the project including the name, genre, technologies used and target audience. They continue by describing that the world and general environment should be included along with a high-level overview of narrative and plot. Furthermore, the gameplay should be outline clearly and should include visual references to help the reader imagine how the gameplay should function and they further express that the document should be as clear and concise as possible. Therefore, nothing should be re-stated within the document.

Since game development is an iterative process, it may be required that the GDD is updated accordingly based on testing and user feedback. Therefore, if the GDD is a larger document and/or focuses on specifics it will substantially require more updates, which would be unsustainable for a small indie studio or a game jam based project. So, it its very important to leave the specifics out and aim to be more general. Danilo Márcio Lima de Carvalho et al gives a good example of this, descriptions such as "the apple gives 30 health points when the player catch it" is too specific and would most likely change after play testing, whereas "many times the player will feel relieved when they catch an apple" is more generalised and unlikely to change[[1](#c1)]. The latter also focuses more on gameplay and experience rather than the low-level values of the system witch often change during the development process.

With that said, if we had created a short GDD at the beginning of the project witch included many of the points from the article [[1](#c1)], we potentially would of ended up with a more complete artifact which integrated all of our original ideas. Furthermore, the overall product would have had a greater chance to get across the message and emotions that we intended to induce on the player. This is simply due to fact, that we would have had a basic outline of the project, the narrative, setting and gameplay, which would of gave us all a shared image of what we were trying to achieve. 

As a result, I feel that we didn’t achieve what we intended, mostly due to the fact we all had a slightly different picture of what we were trying to achieve rather than a collective whole. Therefor it seemed like it was disheartening for the team as it felt like everyone was moving in a different direction and other teams didn’t seem to be having the same issues as us. Up until this point as a programmer I never understood how important a GDD really is, no matter how basic, it serves as a method to convey a shared image of the game. It further ensures that everyone is working towards the same overall outcome and that the product does not go astray from its original goals. In the next small project, I work on (starting next week), there will certainly be more focus put onto creating a GDD before any real development begins to help prevent the mistakes made in this project.


### Cites
##### All citations are available in a single [bibtex file](../references.bib)

<p id="c1">
[1] D. M. L. de Carvalho and F. d. J. L. Gomes, “Simple game design document focuusedon gameplay features,” inXV Brazilian Symposium on Computer Games and DigitalEntertainment, S ̃ao Paulo, vol. 8, no. 10, 2016, pp. 722–725
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
entry_id  = 4
published = "08-10-2021" 
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