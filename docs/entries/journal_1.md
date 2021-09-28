## The Avatar
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

Erler this week we where set a tiny task to create an animated avatar (gif) that would reprasent and have meaning to ones self. My initial idea was to animate my three ruber ducks "swiming" around a cafetiere using stop motion animation [[1](#c1)]. However, after taking several shoots it became apprent that it was a little unaproreate for an acerdemic context. Since, the front runner (and my personal faverate) of the 3 ducks is know as "Stinky Finger" of which depicts a rubber duck sticking it's middle finger up. The second is holding a cup of coffee [fig. 1] while the thrid is the tech support ducky [fig. 2]. (Sorry you'll have to Google [Rubber duck stinky finger](https://www.google.com/search?q=ruber+duck+stinky+finger) yourself). 

The reasion i originaly choose this for my avatar is because it represents a tipical working day in the life of myself (Ashley Sands). "Stink finger" represents how i pritty much feel when my arlam clock first goes off, the coffee duck is the second phase of my day, while the tech support ducky represents me getting to work as a programmer. Another reasion i was influents to use rubber ducks for my avatar is because there a bit of programmers meme, due to a practis knowen as ``Rubber Duck Debbging`` (aka ``Rubber Ducking``) [[2](#c2)][[3](#c3)]. The cafetiere on the other hand, well... i basicly wership the cafetiere, every day starts with at least 2 cups of freshly pressed coffee (or espresso based coffee). Anything less is considered a bad day, though its userly due over-sleeping rather than running out of coffee (i think coffee is the one thing i would panic buy if there where a shortage).  

So i had to change my idea to somthink a little more approrate and to be honest, i was running a little dry on creativity at this point.

I simply, reduced the rubber ducks down to just the coffee duck and switch out the cafetiere for a San Pelleorino water bottle. The ruber duck represents coffee and programming tendencies. While San Pelleorino is what i drink other than coffee (among other soda waters). The two objects simply just rotate around a central point. However originaly, once a full cercil was completed i wanted the water bottal to topal over and smash the duck on the head. But, just befor the bottal hits the duck i wanted to switch out the screen for an image of Windows's fameious **Blue Screen Of Death** (BSOD). Why? you may ask. Well, im a bit randome like that and over the last 9 or 10 months my life has been plaged with various BSOD's to the point i had to get a new machain, since it appered to be a motherboard issue. Though i decided to drop the BSOD idea since it was a little to jarring and dident quite work out how i would of liked (but thats development for you). So i just ended up with the two rotating around a central point [fig. 3].

Although i had created my avatar, i finished much later than i intended, not only because i had to come up with an alternative idea, but due to the fact iv be suffering from a major case of procrastination. 

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
entry_id  = 1
published = "23-09-2021" 
week = 1

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