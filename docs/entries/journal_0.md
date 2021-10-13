## The Frustrations of being Dyslixic
#### Entry <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

This week is the first week back at university after completing a BSc in 'Computing for Games'. Though this time around, I will be undertaking an MSc in 'Artificial Intelligence for Games'. For our first module we have been introduced to development synergies which has been designed to change the way we think about creativity through the process of critical reflection [[1](#c1)]. Critical reflection is a continuous and iterative process of [The process [and/or image]].

In our first workshop, we started off with a couple of icebreakers. Of which, one involved bringing in a sentimental item and describing it to the person sat next to us, where they would take notes, based on the description. Following that we were asked to compile the notes into a short paragraph or story. However, being dyslexic, makes reading and writing a relatively difficult task for myself and therefor it takes me considerably longer to form comprehensive sentences and paragraphs (or at least it feels that way). In general, I’m prepared to put in the extra time required to produce a comprehensive piece, whether it’s an essay, technical report or even something as simple as an email. However, when it comes to producing paragraphs on the fly, I generally fall flat on my face. Either my brain goes blank (I guess due to the pressure) or, as whit this activate, I produce something that is difficult to understand and is much shorter than the rest of the cohort, since I am unable to go through my normal writing process, due to the time constraints. Furthermore, we had to read our short paragraph to the rest of the cohort, which is something I’m not confident with, but in this case, I was dreading it, since I know I had written considerably less from listening to others in the class read theirs back (and mine was an absolute mess on paper, not going to lie). 

Moments such as this are almost always followed by embarrassment and self-doubt ([Some slurs]). Nobody singles me out, laughs at me or whatever, people are generally more considerate these days. However, I think it’s that thing that humans are really good at, comparing ourselves to others. It’s in that moment of realising how sub-par my work is in comparison to the others that these felling of embarrassment and self-doubt originate. I don’t know why it causes me to doubt myself so much. If I look back to when I started my undergraduate 3 years ago, we had to do a similar activity and no matter how hard I tried, I just could not get anything on paper. Absolutely nothing. However, after 3 years of practising to write essays, technical reports, blogs and so forth, has caused my writing to dramatically improve. I mean getting a poorly formed paragraph down is 100% better than nothing, right? It's when I think like this that I realise, that I should not doubt myself or compare myself to others, at end of the day we all have our own skillsets and I just need to further practise my writing. I feel it would be wise to maybe take a writing class to further improve my writing, especially outside of a computing context, as this is pretty much the only real writing experience I have. 

If I’m to be honest, I actually quite enjoy writing about projects and the research that goes into producing the artifact itself. It’s just the dread from knowing how long it takes me to form sentences and paragraphs, along with difficulties I have spelling that makes it hard to get started. Because of these difficulties spelling, I actually tend to do most of my writing in Notepad++, to not be patronized or distracted by Microsoft Words red squiggly line (spell check), reminding me how hard I find spelling. I always feel so inclined to correct the mistake in the first instance which further adds to the difficulties, since it disrupts the flow of thoughts. (I do eventually copy it into Word to correct my speeling and grammar, I just find it distracting while writing)

Anyway, while I was Googling the spelling for dislexic (apparently its spelt 'dyslexic', oh the irony) I stumbled across a lovely quote that I think hits the nail on the head perfectly.

*"Having dyslexia can sometimes make you feel frustrated or sad. With the right help, though, you can learn to read—and even to enjoy reading—and you can be anything you want to be."* [[2](#c2)]
(tho I would like to add ‘write’/’writing’ to that but it’s pretty much spot on, in my opinion) 

And I want to be a programmer, with a strong skillset in distributed systems and AI, find new ways to improve current technologies, the way we interact with media and even each other. However, I feel that I must improve my writing further. I know I can, I’ve proven I can, I just need more practise.

<br />

### Cites
##### All citations are available in a single [bibtex file](../references.bib)

<p id="c1">
[1] University of Waterloo, "Critical Reflection," [Online]. Available: https://uwaterloo.ca/writing-and-communication-centre/critical-reflection, [Accessed: 21 September 2021]
</p>
<p id="c2">
[2] The Yale Center For Dyslexia & Creativity, “On Being Dyslexic,” [Online]. Available: https://dyslexia.yale.edu/resources/dyslexic-kids-adults/on-being-dyslexic/, [Accessed: 21 September 2021] 
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
entry_id  = 0
published = "21-09-2021" 
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