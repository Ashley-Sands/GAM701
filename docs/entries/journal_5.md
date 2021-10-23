## The Importences of sprint planing and scrum
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

In the [last post](./jounal_4) we discussed game design documents for small projects and briefly discussed the importance of the document. In this post I think it would be wise to have a look at scrum and sprint planning as this was another area that we were lacking on that project.

At the start of a new project, I find it can be quite daunting to plan all the individual tasks that are required to achieve a minimal viable product (MVP). Often, I just get excited about a new project and jump straight into the deep end to make things happen and in this case, the others followed suite. This is probably another reason why we lost sight of our goals in the project, we had no defined to-do list or scrum board. It came as a bit of a surprise when we realised that we were missing a couple of aspects from the project and as a result we did make a scrum board, but it was too little too late. This could of be avoided if we had planned our sprint at the start of the project and define a scrum board to our track progress.

So, what is sprint planning and how could we have utilized it to improve our process?

Sprint planning occurs at the start of a sprint usually lasting 2 weeks [[1](#c1)] (although in our case we had 1 week). The purpose of the event is to define what can be achieved within the time frame and who will accomplish the individual tasks. Usually, a sprint planning session is attended by the product owner (PO), the scum master and remaining team. Furthermore, sprint planning should be timeboxed to no longer than 2 hours for a 2-week sprint. However, in our case we were only doing a single week sprint so 1 hour should be sufficient and with the project being so short we don’t have POs.

At the beginning of sprint planning it is necessary to define a sprint goal, so everyone knows what we are working towards, then several tasks need to be assigned to achieve the overall objective. This process should be broken down into several steps to achieve the desired outcome.

- Objective: Define the overall goal for the sprint
  - Tasks: What tasks are required to achieve the objective.
  - How: How will the task be achieved.
  - Who: Who will undertake the tasks.
  - Time: How long will it take to achieve the task.

Often, the hardest part and arguably the most important part of planning is estimating how long it will take to achieve the task, as this can be the different between a successful or unsuccessful sprint. Furthermore, it can indicator if the sprit is realistically achievable or not with the team’s current skill set. Basically, it’s a method of forecasting with the information that is currently available. Often techniques such as t-shirt sizing [[2](#c2)] and planning poker [[3](#c2)] (also known as scrum poker[[3](#c3)] or story points [[4](#c4)]) are used. In T-shirt sizing, each member of the team will place down a t-shirt size which will then give a rough idea of how long the task will take based on the team’s skill set. Moreover, Any T-shirt size that goes above large must be broken down into smaller user stories. In a blog on Medium.com [[5](#c5)] Janaka Fernando give his gives his estimate range for each T-shirt size.

```
XSmall = 1–2 hours
Small = 3–6 hours
Medium = 7–21 hours (1–3 days)
Large = 28–56 hours (4–8 days)
```
[Janaka Fernando, T-shirt estimate range for User stories]

Another important aspect of sprint planning is coming up with users’ stories and I fell that they are often overlooked among university teams. Personality as a programmer I’m not a fan of user stories as there is often overlap in coding tasks, however, I do believe there is merit in the approach. It's all well and good having task such as ``Implement Move Functionality`` or ``Create Run Animation`` but it hard to know what "complete" really means as it’s very vague. User stories overcome this describing the work from the customers or end users’ point of view. A typical user story consists of ``As a <type of user>, I want <a goal> so that <a reason>`` [[5](#c5)][[6](#c6)]. So, the above tasks would become ``As a player, I can move the character to explore the world`` or ``As a player, I want to see the running animation to empathise that I am moving faster``. By defining user stories in this manner, it becomes clear and measurable when the task is complete. As an example, we know ``As a player, I can move the character to explore the world`` is complete when the player can move their character around the world. Furthermore, it is beneficial to break down user stories into the individual tasks that contribute to the outcome such as a to-do list.

## Conclusion
In the short 1-week project that I was working, we failed to do any form of sprint planning. However, we did discuss what needed to be done and tock notes, but we didn’t form a sold plan containing all the tasks that where requires. Furthermore, we didn’t do any form forecasting how long a task would take nor did we have a measurable way of knowing if a task was completed or not. It was a bit of a surprise when we realised, we had missed a few points on the brief which become a bit of a rush at the end to get it implemented and therefor complete. I found it was frustrating not knowing where everyone was in the project and it led to sub-optimal and rushed product. In the future if no one is taking charge of the project planning I will be more assertive and push for a scrum board from the start. Since it allows us to keep track of the project and therefor the product should benefit from the process.


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