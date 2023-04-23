Download Link: https://assignmentchef.com/product/solved-2110215prog-lab3-abstraction
<br>
<strong>Lab 3: Abstraction</strong>

<strong> </strong>

<h1>Instruction</h1>

<ol>

 <li>Click the provided link on MyCourseVille to create your own repository.</li>

 <li>Open Eclipse and then “File &gt; new &gt; Java Project” and set project name in this format</li>

</ol>

<strong>2110215_Lab3_2021_1_{ID}_{FIRSTNAME}</strong>

<ul>

 <li>Example:<strong> 2110215_Lab3_2021_1_6331234521_Jolyne</strong>.</li>

</ul>

<ol start="3">

 <li>Initialize git in your project directory ○ <strong>Add .gitignore. </strong>

  <ul>

   <li>Commit and push initial codes to your GitHub repository.</li>

  </ul></li>

 <li>Implement all the classes and methods following the details given in the problem statement file which you can download from CourseVille.

  <ul>

   <li>You should create commits with meaningful messages when you finish each part of your program.</li>

  </ul></li>

</ol>

○ Don’t wait until you finish all features to create a commit.

<ol start="5">

 <li>Test your codes with the provided JUnit test cases, they are inside package <strong>student</strong> ○ <strong>You have to write some tests by yourself</strong>. Put them inside package <strong>test.student</strong>

  <ul>

   <li>Aside from passing all test cases, your program must be able to run properly without any runtime errors.</li>

  </ul></li>

</ol>

○ There will be additional test cases to test your code after you submit the final version, <strong>make sure you follow the specifications in this document</strong>.

<ol start="6">

 <li>After finishing the program, create a UML diagram and put the result image (<strong>png</strong>) at the root of your project folder.</li>

 <li>Export your project into a jar file called <strong>Lab3_2021_1_{ID}</strong> and place it at the root directory of your project. <strong>Include your source code in the jar file</strong>.

  <ul>

   <li>Example: <strong>jar</strong></li>

  </ul></li>

 <li>Push all other commits to your GitHub repository.</li>

</ol>







<h1>1. Problem Statement: Children’s Card Game</h1>

<strong> </strong>

After your success with creating a toy solar system, you receive an invitation from a toy company, “Wizards of the Rich!”. The company needs your help to create a children’s card game. But this company has no experience making one before (but that does not stop them because they want cash money). So, you decide to make a simple card game for them.

<strong>1.1</strong> Gameplay







In your prototype, a player duels a fixed opponent who never plays any card, which means most of the card functions will only be used by the player.

<h2><strong>1.1.1</strong> <strong>Game Component </strong></h2>

1.Player Character Card

<ul>

 <li>At the start of the game, each player will have a default character as an avatar. You choose Player Character before you choose your deck.</li>

</ul>

Each has different stats of:

<ul>

 <li>Life Point = if Life Point of the character in played reaches 0, the corresponding player loses the game.</li>

 <li>Attack Point = The amount of damage this card deals to the opponent when attacking.</li>

 <li>Defense Point = The amount of damage this card reduces when defending against an opponent’s attack.</li>

</ul>




2.Deck

<ul>

 <li>Contains as many cards as you want, you can insert and remove any card at the card shop. However, you can only have up to 4 of the same cards.</li>

</ul>




<ol start="3">

 <li>Card

  <ul>

   <li>Character Card</li>

  </ul></li>

</ol>

– Similar to player character, Character card contains Life Point, Attack Point, and Defense Point.

Player can choose to perform 1 of 2 actions when playing this card.

<ol>

 <li>           Switch Character

  <ul>

   <li>All of current character’s equipped items will be retired. – Replace current character in play with this card.</li>

   <li>Remaining Life Point percentage from previous character will be transfered to new character. (Ex Current character LP = 75/100 -&gt; New character = 112/150) 2. Sacrifice</li>

   <li>With the cost of this card, you can increase current character Life Point (by percentage). Different types of card increase different percentage of Life Point.</li>

  </ul></li>

</ol>




<ul>

 <li>Basic Character Card

  <ul>

   <li>Character card with only switch and sacrifice actions.</li>

   <li>Sacrificing it heals the current character for 1/6 of the current character’s max LP.</li>

  </ul></li>

 <li>Main Character Card</li>

</ul>

– Character card that can level up when this card is in play and Player               uses the same card. Level up increases all 3 of character stats. – Sacrificing it heals the current character for 1/8 of current character’s  max LP.

<ul>

 <li>Exodia Character Card

  <ul>

   <li>Character card that when equip with 4 Exodia Part Cards (Item Card), Player will immediately win the game.</li>

   <li>Sacrificing it heals the current character for 1/10 of the current character’s max LP.</li>

  </ul></li>

</ul>




<ul>

 <li>Item Card

  <ul>

   <li>Item Card is used to increase character stats, it contains LP bonus, Attack bonus, and Defense bonus.</li>

   <li>Item Card only has 1 action when played, equip item, which increases  the current character’s stats. Character can have any number of item  cards equipped, but all equipped item cards will be lost when player  switches character.</li>

  </ul></li>

</ul>




<ul>

 <li>Basic Item Card</li>

</ul>

– Item card with only previously mentioned function.

<ul>

 <li>Exodia Part Card</li>

</ul>

– Item card that only increases character Defense Point, if this card is              equipped on to Exodia Character Card, Defense Point increase will be              doubled.




<h2><strong>1.1.2</strong> <strong>Game Flow </strong></h2>

At the start of the game, the player shuffles his deck and draw 5 cards. A player character card is played as a placeholder character.

1.Start with the player turn, the player draws a card.

2.Player chooses to play one card and pick its action.

3.Player character automatically attacks opponent character:

– Damage dealt = Attacker’s Total Attack Point – Defender’s Total Defense Point

(Damage can’t be negative)

4.Start the opponent turn, opponent character automatically attacks player character.

5.Repeat until win condition is met by either player.




<ol start="2">

 <li><strong> Implementation Details: </strong></li>

</ol>

To complete this assignment, you need to understand about <strong>Abstract Classes</strong> and <strong><sup> </sup></strong><strong>Junit Test Cases</strong>.

To test your understanding about abstraction, <strong>we will not provide class diagram for this assignment, and we will not indicate which methods and classes are abstract.</strong> Try your best to figure out. There are <strong>three </strong>abstract classes and <strong>three </strong>abstract methods.

There are <strong>five</strong> packages in the provided files: application, player, card, deck and test.

You will be implementing most of the class in the card and deck package (Every class is partly given, while PremadeDeck class doesn’t need to be modified).

There are some test cases given in package test.student. These will help test your code whether it will be able to run or not. However, <strong>some conditions are not tested </strong>in these test cases. <strong>Look for those conditions in the class details</strong>. <strong>You must create your own test cases for such cases.</strong>

<strong>You can define any additional number of <u>private</u> (but not public, protected or package) fields and methods</strong> in addition to the fields and methods specified below. You are encouraged to try to group your logic into private methods to <strong>reduce duplicate code as much as possible</strong>.




<em>* Noted that Access Modifier Notations can be listed below <strong>  + (public), # (protected), – (private)</strong></em>

<strong> </strong>

<strong>2.1</strong> package deck

<h2>1.1.3 <strong>Class: </strong><strong>Deck</strong></h2>

This class represents a deck player will used. Deck has 3 attributes: <strong>name, deckSize, and deckList</strong>. Player can assign deck to use in gameplay. <strong>Deck can</strong> <strong>only have at most 4 of the same cards.</strong>

<ul>

 <li>name = name of the deck</li>

 <li>deckSize = number of cards the deck contains, need to change when Deck is created, when card is inserted into the Deck, and when card is removed from the Deck.</li>

 <li>deckList = list of the cards this deck contains. Each card must be assigned to an array without any empty slot.</li>

</ul>

2.1.1.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="312">+ Deck(String name, Card[] deckList)</td>

   <td width="312">Construct a Deck object with the given name , deckList, and initialize deckSize to be the same size as the given deckList.(Hint: You should use Array (Card[]) to implement inventory.). </td>

  </tr>

 </tbody>

</table>

2.1.1.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="312">+ int insertCard(Card card)  throws InsertCardFailedException</td>

   <td width="312">Insert the given card into <strong>the bottom of card list (Recommend: create a new copy of deckList array with one more slot)</strong> and modify deckSize to be accurate to the new deckList. Throw an InsertCardFailedException with message <em>“</em>You can only put 4 of the same cards into the deck<em>”</em> if there are already 4 of the same card in the deck. Otherwise, return the new deckSize. (Given, but can be changed or adjusted according to how you code insert card).

    <table width="299">

     <tbody>

      <tr>

       <td colspan="2" width="299">Hint: You can use isEqual(Card othercard) method</td>

      </tr>

      <tr>

       <td width="95">from Class card.</td>

       <td width="204"></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

  <tr>

   <td width="312">+ Card removeCard(int slotNumber) throws RemoveCardFailedException</td>

   <td width="312">Unequip a card in the given slot number from the deck, rearrange the card from every slot after it to replace the empty slot. Modify deckSize to be accurate to the new deckList, and return the removed card.</td>

  </tr>

  <tr>

   <td width="312"></td>

   <td width="312"> Throw an RemoveCardFailedException with message “Number you insert exceed deck size” when the slotNumber is greater than or equal to deckSize. (Already Implemented)</td>

  </tr>

  <tr>

   <td width="312">+ String toString()</td>

   <td width="312">You do <strong>not</strong> have to edit this method.</td>

  </tr>

  <tr>

   <td width="312">+ int Card[] getDeckList()+ int String getName()+ int getDeckSize()</td>

   <td width="312">Getter methods.</td>

  </tr>

  <tr>

   <td width="312">+ void setDeckSize(int deckSize)</td>

   <td width="312">Setter method.</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h2><strong>2.2 </strong>package card.base</h2>

<h3>2.2.1 Class Card</h3>

This class is the base class of all cards in the card shop. Each card has its own name and description. Card <strong>should never be instantiated into objects</strong>, as it is only designed to be a base class so that consumer classes (like Deck) can easily use their subclasses.

2.2.1.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="296">+ Card(String name, String Description)</td>

   <td width="328">Initialize the card with the given name and description.</td>

  </tr>

 </tbody>

</table>

2.2.1.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="294">+ String toString()</td>

   <td width="330"><strong>this method should never be called with from this card, it can only be called from subclasses.</strong></td>

  </tr>

  <tr>

   <td width="294">+ String getName()+ String getDescription()</td>

   <td width="330">Getter methods.</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h4>2.2.2 Class CharacterCard</h4>

This class is a base class of character card, used as an avatar for player to use in gameplay. It has lifePoint, attackPoint, and defensePoint. It provides shared implementation of displaying names across all upgradable items. CharacterCard <strong>should never be instantiated to objects, </strong>as it is only designed to be a base class so that consumer classes (like the Deck and Player) can easily use their subclasses.

<strong> </strong>

2.2.2.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="296">+ CharacterCard (String name, String Description , int lifePoint, int attackPoint, int defensePoint)</td>

   <td width="328">Initialize the character card with the given name , description, lifePoint, attackPoint, and defensePoint.</td>

  </tr>

 </tbody>

</table>

2.2.2.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="294">+ void switchCharacter(Player player)</td>

   <td width="330">Switch character of the player, which also include changing player lifePoint, attackPoint, and defensePoint using those of the card. Hint:Use <u>setNewCharacterLifePoint(int)</u>,setAttack<u>(int)</u>, setDefense <u>(int)</u>, setAssignedCharacter <u>(CharacterCard)</u> from Player class. setNewCharacterLifePoint already uses percentage calculation. It will change current life point from player’s previous life point already. You can simply insert lifepoint into this method.</td>

  </tr>

  <tr>

   <td width="294"><em>+ </em>int sacrifice(Player player)</td>

   <td width="330">Called when using CharacterCard to increase player life point. Life point gain is different for each class<strong> this method should never be called from this class. It can only be called from subclasses.</strong></td>

  </tr>

  <tr>

   <td width="294">+ String toString()</td>

   <td width="330">You do <strong>not</strong> have to edit this method.</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h3>2.2.3 Class ItemCard</h3>

This class is a base class of item card, a player can equip item to increase lifePoint, attackPoint, and/or defensePoint. It has lpBonus, attackBonus, and defenseBonus. It provides shared implementation of displaying names across all item cards. ItemCard <strong>should never be instantiated to objects, </strong>as it is only designed to be a base class so that consumer classes (like the Deck and Player) can easily use their subclasses.

<strong> </strong>

2.2.2.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="296">+ ItemCard(String name, String description, int lpBonus , int attackBonus, int</td>

   <td width="328">Initialize the item card with the given name ,description, lpBonus, attackBonus, and</td>

  </tr>

  <tr>

   <td width="296">defenseBonus)</td>

   <td width="328">defenseBonus</td>

  </tr>

 </tbody>

</table>

2.2.2.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="294"><em>+ </em>void equipItem(Player player)</td>

   <td width="330">Called when using ItemCard to increase player stats.<strong> This method should never be called from this class. It can only be called from subclasses.</strong></td>

  </tr>

  <tr>

   <td width="294">+ String toString()</td>

   <td width="330">You do <strong>not</strong> have to edit this method.</td>

  </tr>

 </tbody>

</table>




<strong> </strong>

<h2><strong>2.3 </strong>package card.cards</h2>




This package contains implementation of the <strong>concrete </strong>card in card shop. Some classes should be extended from card.base package while some should be extended from this package. In any case, every class must be extended from Card class at its root.




<h3>2.3.1 Class BasicCharacterCard</h3>

This class represents “basic character card” that has no additional logic or properties




2.3.1.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="294">+  BasicCharacterCard (String name, String description, int lifePoint, int attackPoint, int defensePoint)</td>

   <td width="330">Initialize the basic character card with the given name, description, and other attributes.</td>

  </tr>

 </tbody>

</table>

2.3.1.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="293"><em>+ </em>int sacrifice(Player player)</td>

   <td width="331">Called when using BasicCharacterCard to increase player life point. Life point gain is different for each class<strong>  </strong><strong>Return life point increased from this method </strong>(Do not have to consider whether healing lifePoint exceed maxLifePoint)<strong>The player is healed equal to 1/6 of player maxLifePoint </strong>

    <table width="153">

     <tbody>

      <tr>

       <td width="32">Hint:</td>

       <td width="121"></td>

      </tr>

      <tr>

       <td colspan="2" width="153">Use getMaxLifePoint<u>()</u></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

  <tr>

   <td width="293"></td>

   <td width="331">


    <table width="125">

     <tbody>

      <tr>

       <td colspan="2" width="125">, healPlayer<u>(int)</u></td>

      </tr>

      <tr>

       <td width="110">from Player class</td>

       <td width="15"></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h3>2.3.2 Class BasicItemCard</h3>

This class represents “basic items card” that has no additional logic or properties

2.3.1.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="294">+  BasicItemCard(String name, String description, int lpBonus, int attackBonus, int defenseBonus)</td>

   <td width="330">Initialize the item card with the given name, description, and the attribute bonuses.</td>

  </tr>

 </tbody>

</table>

2.3.1.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="293"><em>+ </em>void equipItem(Player player)</td>

   <td width="331">Called when using this card to increase player stats<strong> and add this ItemCard to player inventory. In case of lpBonus, it must apply on both player’s currentLifePoint and maxLifePoint.</strong> Hint:Use addInventory<u>(Itemcard)</u>, setMaxLifePoint<u>(int)</u>, setCurrentLifePoint<u>(int)</u>, setAttack<u>(int)</u>, setDefense<u>(int)</u> from Player class</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h3>2.3.3 Class MainCharacterCard</h3>

This class represents “main character card”. Very similar to CharacterCard but with 2 more properties and 3 more methods. Main character start with level 0. If a player currently plays main character card, it can <strong>levelUp,</strong> which increases level by 1 and increases player stats equal to <strong>levelUpBonus multiplier</strong>. (levelUp can be done by playing the same card as the main character card, but you don’t have to implement that part).

<ul>

 <li>int level = current level of this character, start with 0 when initialized</li>

 <li>float levelUpBonus = stat increase multiplier when levelUp,</li>

</ul>

Ex: If levelUpBonus = 0.3, when levelUp, player lifePoint, attackPoint, and defensePoint increase by 30% (round down to int)

2.3.3.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="294">+  MainCharacterCard (String name, String description, int lifePoint, int attackPoint, int defensePoint, float levelUpBonus)</td>

   <td width="330">Initialize the main character card with the given name, description, levelUpBonus, and the attribute.</td>

  </tr>

 </tbody>

</table>

2.3.3.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="293"><em>+ </em>int sacrifice(Player player)</td>

   <td width="331">Called when   using    MainCharacterCard    to increase player life point. Life point gain is different for each class.<strong>  </strong><strong>Return life point increased from this method </strong>(don’t have to consider whether healing lifePoint exceed maxLifePoint)<strong> </strong><strong>Player is healed equal to 1/8 of player maxLifePoint. </strong>Hint:Use getMaxLifePoint<u>()</u> , healPlayer<u>(int)</u> from Player class</td>

  </tr>

  <tr>

   <td width="293">+ float levelUp(Player player) </td>

   <td width="331">Called when using MainCharacterCard to <strong>increase lifePoint, attackPoint, and defensePoint equal to its multiplier with levelUpBonus. Also increase level by 1. </strong><strong> </strong><strong>Return levelUpBonus </strong>Ex: If levelUpBonus = 0.3, when levelUp, player lifePoint, attackPoint, and defensePoint increase by 30% (round down to int). Lifepoint increases from maximum lifepoint. Hint:Use <u>setNewCharacterLifePoint (int)</u>, setAttack<u> (int)</u>, setDefense<u> (int)</u> from Player class


    <table width="318">

     <tbody>

      <tr>

       <td colspan="2" width="318"><u>setNewCharacterLifePoint(int)</u> method will change current life point from player previous life point already. You can simply insert lifepoint into this</td>

      </tr>

      <tr>

       <td width="51">method.</td>

       <td width="267"></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

  <tr>

   <td width="293">+ String getName()</td>

   <td width="331">You do <strong>not</strong> have to edit this method.</td>

  </tr>

  <tr>

   <td width="293">+ int getLevel()</td>

   <td width="331">Getter methods.</td>

  </tr>

  <tr>

   <td width="293">+ void setLevel(int level)</td>

   <td width="331">Setter methods.</td>

  </tr>

 </tbody>

</table>

<h3>2.3.4 Class ExodiaCharacterCard</h3>

This class represents “exodia character card”. Exodia is a CharacterCard with: name = “”Exodia the Forbidden One”” description = “With 4 or more Exodia Part Card equiped, you win the game” lifePoint = 800 attackPoint = 0 defensePoint = 25

Additionally, it has one more method called winConditionCheck that check if Exodia is equip with 4 ExodiaPartCard or not. If it’s true, player win the game immediately (You don’t have to implement winning part, you only have to return true or false).

2.3.4.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="294">+  ExodiaCharacterCard()</td>

   <td width="330">Initialize the main character card with the given name, description, and the attribute.(See above)</td>

  </tr>

 </tbody>

</table>

2.3.4.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="293"><em>+ </em>int sacrifice(Player player)</td>

   <td width="331">Called when using       ExodiaCharacterCard to increase player life point. Life point gain is different for each class<strong>  </strong><strong>Return life point increased from this method </strong>(don’t have to consider whether healing lifePoint exceed maxLifePoint)<strong> </strong><strong>Player is healed equal to 1/10 of player maxLifePoint. </strong>Hint:Use getMaxLifePoint<u>()</u> , healPlayer<u>(int)</u> from Player class</td>

  </tr>

  <tr>

   <td width="293">+ boolean winConditionCheck(ItemCard[] inventory) </td>

   <td width="331">

    <table width="318">

     <tbody>

      <tr>

       <td width="32">Hint:</td>

       <td width="286"></td>

      </tr>

      <tr>

       <td colspan="2" width="318">Use <u>instanceof to check if ItemCard is</u></td>

      </tr>

     </tbody>

    </table>Called to check if the inventory contains 4 or more ExodiaPartCard. Return true if it has 4 or more, false otherwise. </td>

  </tr>

  <tr>

   <td width="293"></td>

   <td width="331"><u>ExodiaPartCard</u></td>

  </tr>

 </tbody>

</table>

<h3>2.3.5 Class ExodiaPartCard</h3>

This class represents “exodia items card” Exodia is an ItemCard with: description = “Assemble 4 of Exodia part card to win the game” lifeBonus = 0 attackBonus = 0

name and defenseBonus depends on initialization

2.3.5.1 Constructors

<table width="624">

 <tbody>

  <tr>

   <td width="294">+  ExodiaPartCard(String name, int defense)</td>

   <td width="330">Initialize the main character card with the given name, description, and the attributes.(See above)</td>

  </tr>

 </tbody>

</table>

2.3.5.2 Methods

<table width="624">

 <tbody>

  <tr>

   <td width="293"><em>+ </em>void equipItem(Player player)</td>

   <td width="331">Called when using this card to increase player stats<strong> (only defensePoint in this case) and add this card to player inventory. </strong><strong>If player character is ExodiaCharacterCard, increase player stats by twice of this bonus stats instead</strong> Hint:Use addInventory<u>(Itemcard)</u>, setMaxLifePoint<u>(int)</u> , setDefense<u>(int)</u> , getAssignedCharacter() from Player classUse <u>instanceof to check if player’s</u><u>CharacterCard is ExodiaCharacterCard</u></td>

  </tr>

 </tbody>

</table>

<strong> </strong>




<h2><strong>2.4 </strong>package test.student</h2>

<h3>2.4.1 Class TestDeck</h3>

This class test Card class from card.base package. All constructors and some test cases has already been implemented, <strong>except for 2 test cases which student needs to implement.</strong>

2.4.1.1 Methods (Test cases)

<table width="624">

 <tbody>

  <tr>

   <td width="294">+ void testRemoveCard()</td>

   <td width="330"><strong>This test case must test 2 scenarios.</strong>1.                  Remove any card from the deck, then check if that card inside the deck is no longer there, number of cards is reduced, and other cards are rearranged correctly.2.                  Repeat scenario 1, but with a different deck.</td>

  </tr>

  <tr>

   <td width="294">+ void testRemoveNonExsistanceCard ()</td>

   <td width="330">Use             assertThrows             to              checkRemoveCardFailedException by removing card form the deck on the slot that doesn’t have card in it.</td>

  </tr>

 </tbody>

</table>




<h4>2.4.2 Class TestExodiaCharacterCard</h4>

This class test ExodiaCharacterCard class from card.cards package. All constructors and some test cases has already been implemented, <strong>except for 3 test cases which student needs to implement.</strong>

2.4.2.1 Methods (Test cases)

<table width="624">

 <tbody>

  <tr>

   <td width="294">+ void testSwitchCharacter ()</td>

   <td width="330">Switch player’s character to Exodia, and check if player’s stats is the same asExodiaCharacterCard.</td>

  </tr>

  <tr>

   <td width="294">+ void testSacrifice () </td>

   <td width="330">Set player’s life point not to be full, and sacrifice Exodia to player and check if player’s life point increases accordingly.</td>

  </tr>

  <tr>

   <td width="294">+ void testWinConditionCheck () </td>

   <td width="330">Use winConditionCheck on different ItemCard array (already given) and check if results are correct for each array.</td>

  </tr>

 </tbody>

</table>




<h4>2.4.3 Class TestExodiaPartCard</h4>

This class test ExodiaPartCard class from card.cards package. All constructors and some test cases has already been implemented, <strong>except for 1 test case which student needs to implement.</strong>

2.4.3.1 Methods (Test cases)

<table width="624">

 <tbody>

  <tr>

   <td width="294">+ void testEquipItemExodiaCase ()</td>

   <td width="330">Switch player’s character into Exodia and equip 3</td>

  </tr>

  <tr>

   <td width="294"></td>

   <td width="330">different ExodiaPartCards to it, and check if player’s Defense increase accordingly.</td>

  </tr>

 </tbody>

</table>




<h4>2.4.4 Class TestMainCharacterCard</h4>

This class test MainCharacterCard class from card.cards package. All constructors and some test cases has already been implemented, <strong>except for 2 missing and 1 incomplete test cases which student needs to implement.</strong>

2.4.2.1 Methods (Test cases)

<table width="624">

 <tbody>

  <tr>

   <td width="294">+ void testSwitchCharacter ()</td>

   <td width="330">Switch player’s character into testMainChar, and check if player’s stats is the same as testMainChar</td>

  </tr>

  <tr>

   <td width="294">+ void testSacrifice () </td>

   <td width="330">Set player’s life point to not be full, and sacrifice testMainChar to player and check if player’s life point increases accordingly.</td>

  </tr>

  <tr>

   <td width="294">+ void testLevelUp ()(Given, but incomplete) </td>

   <td width="330">The code already tests levelUp method once from level 0 to level 1. Student must use levelup method on player again and check player’s stats and level when moving from level 1 to level 2.</td>

  </tr>

 </tbody>

</table>








