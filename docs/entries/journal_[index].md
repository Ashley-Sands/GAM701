## [Tital Goes Here] - Journal Entry Template 
#### Entry [<span id="index"></span>], Published: [<span id="published"></span>]

[< Return to index ](../)

### Sub-Heading

This is a template for journal entries to help keep consistency!  
[Page content goes here]

<span id="priv_entry"></span>

[<Return to index](../)

<a id="next_entry" href="">Next ></span>

<script>
// Store the entry id and published values in a JS script, to make life easier with updateing links.
entry_id  = 0
published = "" 

document.getElementByID("entry_index").innerHTML = entry_id
document.getElementByID("published").innerHTML   = published

next_id = entry_id + 1
priv_id = entry_id - 1

// TODO: need to find a way to prevent next page link if on last entry
// Maybe i could just use the js fetch API to see if it returns an error or not.
document.getElementByID("next_entry").href = "journal_"+ next_id

// only display the priv page link if we have gone past the first page.
if ( priv_id > 0)
    document.getElementByID("priv_entry").innerHTML = '<a href="journal_'+priv_id+'">< Priv</a>'

</script>