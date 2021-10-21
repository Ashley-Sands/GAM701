## The Importences of sprint planing and scrum
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

In the [last post](./jounal_4) we discussed game design documents for small projects and brefily discussed the importence of the document. In this post i think it would be wise to have a look at scrum and sprint planning as this was another area that we where lacking on that project.

At the start of a new project I find it can be quite dounting to plan all the indervidule tasks that are required to achaive a minimal viabal product (MVP). Offten i just get excited about a new project and jump streat into the deep end to make things happen and in this case, the others followed suite. This is proberbaly another reasion why we lost sight of our goals in the project, we had no defined todo list or scrum board. It came as a bit of a suprise when we relised that we where missing a couple of aspects from the project and as a result we did make a scrumboard, but it was to little to late. This could of be avoided if we had planned our sprint at the start of the project and define a scrum board to our track progress.

So what is sprint planning and could we of utilataized it to improve our process?

Sprint planning occures at the start of a sprint userly lasting 2 weeks [[1](#c1)] (althout in our case we had 1 week). The purpose of the event is to define what can be achived within the time frame and who will accomplish the indervidule tasks. Userly a sprint planning session is attended by the product owner (PO), the scum master and remaing team. Furthermore sprint planing should be timeboxed to no longer than 2 hours for a 2 week sprint. However in our case we where only doing a single week sprint so 1 hour should be sufficent and with the project being so short we dont have POs.

At the begining of sprint planing it is nessesary to define a sprint goal, so everyone knows what we are working towards, then several taks need to be assigned to achive the overrall objective. This process needs to be brocken down into serveral steps to achavie the deired outcome.

- Objective: Define the overral goal for the sprint
  - Tasks: What tasks are required to achive the objective.
  - How: How will the task be achive.
  - Who: Who will undertake the taks.
  - Time: How long will it take to achive the task.

Offten, the hardest part and arrgubaly the most importent part of planing is extimating how long it will take to achive the task, as this can be the different between a successful or unsuccessful sprint. Furthermore, it can indercater if the sprit is realisticaly achiveable or not with the teams current skill set. Basicly its a method of forcasting with the information that is currently available. Offtern techniques shuch as t-shirt sizing [[2](#c2)] and planning poker [[3](#c2)] (also know as scrum poker[[3](#c3)] or story points [[4](#c4)]) are used. In T-shirt sizing, each member of the team will place down a t-shirt size which will tehn give a rough idea of how long the task will take based on the teams skill set. Moreover, Any T-shirt size that goes above large must be brocken down into smaller userstories. In a blog on Medium.com [[5](#c5)] Janaka Fernando give his gives his estimate range for each T-shirt size.

```
XSmall = 1–2 hours
Small  = 3–6 hours
Medium = 7–21 hours (1–3 days)
Large  = 28–56 hours (4–8 days)
```
[Janaka Fernando, T-shirt stimate range for User stories]

Another imprtent aspect of sprint planning is coming up with users stories and i fell that they are offten overlooked among university teams. Personaly as a programmer im not a fan of user stories as there is offten overlap in coding tasks however, I do belive there is mertit in the approch. It's all well and good having task such as ``Implerment Move Functionality`` or ``Create Run Ainmation`` but it hard to know what "complete" realy mean as its a very vage. User stories overcome this describong the work from the customers or end users point of view. A typical user storie consistes of ``As a <type of user>, i want <a goal> so that <a reason>`` [[5](#c5)][[6](#c6)]. So the above tasks would become ``As a player, i can move the caracter to explore the world`` or ``As a player, i want to see the running animation to empahise that i am moving faster``. By defining userstories in this manner it becomes clear and measurble when the task is complete. As an example we know ``As a player, i can move the caracter to explore the world`` is compleat when the player can move there caracter around the world. Furthermore, it is benifical to break down userstories into the indervidule tasks that contubute to the outcome shuch as a todo list.

## Conclusion
In the short 1 week project that i was working, we failed to do any form of sprint planing. However, we did discuss what needed to be done and tock notes but we did'ent form a sold plan containing all the tasks that where requires. Furthermore, we dident do any form forcasting how long a task would take nor did we have a measurble way of knowing if a task was completed or not. It was a bit of a suprise when we relised we had missed a few points on the brife which become a bit of a rush at the end to get it implermented and therefor complete. I found it was frustrating not knowing where everone was in the project and it lead to sub-optumal and rushed product. In the furture if no one is taking charge of the project planning i will be more assertive and push for a scrum board from the start. Since it allows us to keep track of the project and therefor the pruduct should benifit from the process. 

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