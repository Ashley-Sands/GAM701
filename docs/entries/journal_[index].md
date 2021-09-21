## [Tital Goes Here] - Journal Entry Template 
#### Entry [<span id="index"></span>], Published: [<span id="published"></span>]

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>


### Sub-Heading

This is a template for journal entries to help keep consistency!  
[Page content goes here]


<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

<script>
// Store the entry id and published values in a JS script, to make life easier with updateing links.
entry_id  = 1
published = "dd-mm-yy" 

document.getElementById("index").innerHTML = entry_id
document.getElementById("published").innerHTML   = published


next_id = entry_id + 1
priv_id = entry_id - 1

next_links = document.getElementsByClassName("next_entry")
priv_links = document.getElementsByClassName("priv_entry")

// TODO: need to find a way to prevent next page link if on last entry
// Maybe i could just use the js fetch API to see if it returns an error or not.
for ( let i in next_links )
    next_links[i].innerHTML = '<a href="journal_'+next_id+'">Next ></a>'

// only display the priv page link if we have gone past the first page.
for ( let i in priv_links )
    priv_links[i].innerHTML = '<a href="journal_'+priv_id+'">< Priv</a>' )


</script>