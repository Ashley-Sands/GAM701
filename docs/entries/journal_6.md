## A Tecnical look at A/B testing 2 controller schemes with a GH controller.
#### Entry: <span id="index"></span>, Published: <span id="published"></span>

<span class="priv_entry" style="display: inline;"></span>
| 
[Return to index](../)
| 
<span class="next_entry" style="display: inline;"></span>

We have been set another short project and where asked to begin thinking about ideas releating to culture and society. Furthermore, we also had to think of some technical asspects or aesthetics that we would like to work on. In a workshop we where asked to complile our ideas into a Mural board shared among the cohort, which we would then become a market place of ideas. We then had to choose some of the ideas we liked and form teams to begin producing a game artifact. My Mural board consisted of meny idea based around conspiracy theories, religon, 90s and corperation for the cultureal aspect; real-time audio synthesis, flocking (AI) for technical and old school comic books as an aesthetic [fig. 1]. 

[fig. 1][Mural board]

Looking back i may of missed the point a little, as most people just focused on developing a single idea around a cultural and technical/aesthetic aspect, however i had few randome ideas. The first was to was to re-imagin how physics would work on a flat earth in a sola system based around our current understanding. You would then have to protect the flat earth form extraterrestrials and UFOs. The second idea was to have a island with a road network and serval cities, the player would have to place work and events around island conntected to roads witch the citazens would have to travle to. The player would have to serticly place the work and event locations around to prevent grid lock, which would become gameover.

However, most other ideas in the cohort where much more delveloped than mine, therefor i joined another group. Which to be honest had quite a good idea in my opinion. It was to create a punk rock theamed streat fighter game, wich uses a guirtur hero controller. Furthermore, each scene would be set in a commic strip (simular to comix zone[fig. 2][[1](#c1)]) which is all ilastrated using pixle art. During our initatial sprinting planning session two different controller schemas where mentioned. The first schema [fig. 3] aims to make you feel like your playing the guitar to fight while the second schema [fig. 4] takes a more traditional approch to give instance feedback to the player.

[Fig.2 Comix zone]
[Fig.3 controller schema 1]
[Fig.4 controller schema 2]

Basicly in the first schema you hold down an attack button and strum to active the atack, strum up to jump and down to crouch and use to of the buttons to move. While on the second schema you just press the attack buttons to activate the attack, strum up and down to move and use the to remaining two buttons to jump and crouch. As a team we couldent come to an agreement on which schema to use, through we where leaning towards the more traditional approch. However, we decided to do some A/B testing to see weather players perfered one over the other. This ment i now how to find a way to implerment two different controller schemas without have two different code bases.

### Implermenting the Controler Schema

To begin i configure the two controllers in the new unity inputs system [[2](#c2)] as it allows different action maps (or controller groups). In this case configured it as ``player_1`` and ``player_2`` [fig. 5] each maped to its own Guirtar hero controller, in this case this was quite simple since both controler are from different version of the game making it easy to disiglish between the two. Once i had defined the inputs for the two controllers i had to find a way to access the two action maps consistently without having too much dupulcat code. So i decided to implment each input as a property which selects the correct action map based on the player number [listings. 1].

[fig 5. Unity inputs action maps.]

```
    //...

	public enum Player{ One=-1, Two=1 }			// define as -1 and 1 since it the player multiplyer for direction and power attack
	public Player playerNumber = Player.One;

	// Inputs
	protected float Green  => (playerNumber == Player.One ? inputSchem.Player1.Green  : inputSchem.Player2.Green ).ReadValue<float>();
	protected float Red    => (playerNumber == Player.One ? inputSchem.Player1.Red    : inputSchem.Player2.Red   ).ReadValue<float>();
	protected float Yellow => (playerNumber == Player.One ? inputSchem.Player1.Yellow : inputSchem.Player2.Yellow).ReadValue<float>();
	protected float Blue   => (playerNumber == Player.One ? inputSchem.Player1.Blue   : inputSchem.Player2.Blue  ).ReadValue<float>();
	protected float Orange => (playerNumber == Player.One ? inputSchem.Player1.Orange : inputSchem.Player2.Orange).ReadValue<float>();

    protected float Strum_up   => (playerNumber == Player.One ? inputSchem.Player1.Strum_up   : inputSchem.Player2.Strum_up  ).ReadValue<float>();
	protected float Strum_down => (playerNumber == Player.One ? inputSchem.Player1.Strum_down : inputSchem.Player2.Strum_down).ReadValue<float>();

	protected float Wham => (playerNumber == Player.One ? inputSchem.Player1.Wham : inputSchem.Player2.Wham).ReadValue<float>();

    //...
```
[listings. 1, Inputs properties which sellects the correct action map]

Following this i decided to just implerment the more traditional schema (schema 2) as it is a little simpler and would alow me to develop the basic structre and functionality for each action. Therefor i implermented each action so it has an entry, hold and exit state [listing. 2].

```
    // ...

	private void Punch()
	{

		if (Red > 0 && !redDown && CurrentAction == Actions.None)   // entry
		{
			CurrentAction = Actions.Punch;
			animator.SetTrigger("Punch");
			redDown = true;
		}
		else if ( CurrentAction == Actions.Punch )                  // hold
		{
			// do hit box stuff :)
		}
		else if ( Red == 0 && redDown )                             // exit
		{
			redDown = false;
		}

	}

    // ...
```
[listings. 2, Punch method with the entry, hold and exit states]

Each action (Jump, Crouch, Punch, Kick, Headbutt) is almost the same as puch [listings. 2] except they set the relevent animations and button presses. Now i had to find a way to implerment the other controler scheme without duplicating the code. So i went about making the ``Player`` class abstract, so i could extend the functinality. Originaly i decided to add virtual method for each state so i could also check if the player strumed while pressing the action key [listing. 3].

```
private void Punch()
	{
		// Red
		// Play Punch Animation
		if (Red > 0 && !redDown && CurrentAction == Actions.None)
		{
			
			redDown = true;
			PrePunch();
			
		}
		else if ( CurrentAction == Actions.Punch )
		{
			RunPunch();
		}
		else if ( Red == 0 && redDown )
		{
			redDown = false;
			damageApplied = false;
			PostPunch();
		}

	}

	// i have choosen to implerment these as viertul incase theres notting to implerment in the inherited class.
	protected virtual void PrePunch() 
	{
		CurrentAction = Actions.Punch;
		animator.SetTrigger("Punch");
		SendDamage(punchDamage);
	}

	protected virtual void RunPunch() 
	{
		SendDamage(punchDamage);
	}

	protected virtual void PostPunch() {}

```
[listings. 3 added virtual method for each action state.]

However i soon relised this was more complercated than it needed to be, and there was no intention of extending the functionaliy of the action except for checking if strum is up/down. Therefor i racked my brain a bit more to find a more logical solution, i thourth it might be better to replace the if statment condistion with abstract methods (for enter and exit) [listings. 4] so that they can be implermented in a child class [listings. 5].

```
	private void Punch()
	{
		// Red
		// Play Punch Animation
		if ( EnterPunch() )
		{
			
			redDown = true;
			CurrentAction = Actions.Punch;
			animator.SetTrigger("Punch");
			SendDamage(punchDamage);

		}
		else if ( CurrentAction == Actions.Punch )
		{
			SendDamage(punchDamage);
		}
		else if ( ExitPunch() )
		{
			redDown = false;
			damageApplied = false;
		}

	}

	protected abstract bool EnterPunch();

	protected abstract bool ExitPunch();
```
[listings. 4, added abstract method for enter and exist condisions]

this now ment i could simple inherit form the ``Player`` class and just implerment the Enter and Exit condisions for each controller schema [listings. 5][listings. 6]

```
	protected override bool EnterPunch()
	{

		bool struming = Strum_up > 0 || Strum_down > 0;

		return struming && Red > 0 && !redDown && CurrentAction == Actions.None;
	}

	protected override bool ExitPunch()
	{
		return Strum_up == 0 && Strum_down == 0;
	}
```
[Listings. 5, Player Controle schema 1, enter exit methods for punch]

```
	protected override bool EnterPunch()
	{
		return Red > 0 && !redDown && CurrentAction == Actions.None;
	}

	protected override bool ExitPunch()
	{
		return Red == 0 && redDown;
	}
```
[Listings. 6, Player Controle schema 2, enter exit methods for punch]

This now ment all i had to do was created a ``BasePlayer`` prefab and attach the relevent player controler schema to a prefab veriant of the ``BasePlayer`` and furthermore, add them to there own scene. Then we ready to build the project and A/B test.

### A/B Testing
To begin with the A/B testing, we asked several people (about 10 in total) ato play through the two controller schemas. We got quite a mixed bag or responces which wasent nessesarly what we expected. We expected that most people would perfer the traditional schema (schema 2), however what we found was the more "casule" players prefered the traditional schema while the more "hardcore" players liked the protencal of the guirtar scheme (schema 1). In genral everone seemed to really liked how responceive the traditional schema was, in the sence that you press a button and it attacks, however the people that liked the guirtar scheme found it was very satifying to strum to trigger the attack. They also felt there was more to build on using the guirtar scheme for example, struming down could trigger an over arm punch while struming up would preform an under arm punch (or upper cut). However, players did find some protental issues with the guirtar scheme, because jump is mapped to strum up without pressing an action button it made it extreamly hard to preform jump, attack combos, which is an importent aspect of games such as street fighter. Whatsmore, we found that people with smaller hands found it hard to move forwards and backwards in the guirtar scheme or to jump and crouch in the traditional schema because they where mapped to the top and bottom buttons resptivly. We did want to make switching between the two action to be hard, however it wasent recived well by the players, so we had a meeting to discuss solutions for the points rasied.

To start because the responces where so mixed we decied that we should have two game modes, "casule" (traditional schema) and "punk" (guirtar scheme). We then disscused how we could resolve the minor issues raised and came up with quite an easy solution for the move (guirtar scheme) and jump/crouch (traditional schema) buttons. We decided to just move them to the top two buttons and have the attack actions as the bottom 3 buttons. Furthermore to resolve the jump combo issue we think it would be worth moving it to the the wammy bar on the controller and we would do further A/B testing in the future. 

### Conclusion
At first i found it quite dounting having to find a way to create two different controller schemas, but affter coming up with a relativly simple solution it was pretty straight forwards to implerment. Furthermore, iv never really done any form of A/B testing, however, i now see that it is one of the valubale things a developer can do to get player insight into two different systems. Whatsmore, we dident expect that the guirtar scheme would be as well recived as it was due to its protencal, althouth it needs a little more refining. I will defently do more A/B testing in the furture as its been a very plesent experance to gain insights.

<!-- 
Notes:
- need to add figs of play testing.
- and maybe a vedio of gameplay!
-->

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
entry_id  = 6
published = "18-10-2021" 
week = 5

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