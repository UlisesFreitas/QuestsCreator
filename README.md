# QuestsCreator
Quests Creator Extension for GDevelop 5
Create quests easily With Quests Creator, you can easily create quests for your game. For example collect 3 coins, or kill 3 zombies.
## How to use
* 1 - Start Quests Creator with the function `Init Quests Creator` "At the begin of the scene"
* 2 - Create a quest with `(Collect) Create quest` add the parameters requested by the action.
* 3 - Use the `Check if all objects are collected` action to keep the count of the object you want to collect up to date.
You will have to create your own UI and assign the fields that you want to be visible in your scene.

### Fields available
* `Title` typeof `String`
* `Description` typeof `String`
* `Status` (Active, Inactive, Completed, Failed) typeof `String`
* `CanAbandon` typeof `Boolean` `True|False`

### Expressions that return the current value
** Tip: You will have to pass the quest ID parameter.
* QuestsCreator::Title(Variable(QuestID)) Return `String`
* QuestsCreator::Description(Variable(QuestID)) Return `String`
* QuestsCreator::Status(Variable(QuestID)) Return `String`
* QuestsCreator::CanAbandon(Variable(QuestID)) Return `Boolean`
* QuestsCreator::ToCollect(Variable(QuestID)) Return `Number` returns the value of objects to collect.
* QuestsCreator::Collected(Variable(QuestID)) Return `Number` Returns the total value of objects collected.
* QuestsCreator::Collect(Variable(QuestID)) Return increments the +1 value of collected.

### Actions
* `Ìnit Quests Creator` Starts the Quests Creator engine and sets the scene variable `QuestsCreator`
* `Save` - Save all data to the `QuestsCreator` scene variable
* `LoadAll` - Load all data from the `Storage` into the `QuestsCreator` scene variable
* `(Collect) Create a new quest` - Create a new quest.
* `Find a quest by ID` - Find a quest by its ID, this action also creates a scene variable called `Quest` and saves the data of that quest in it. You can then access using Quest.ID or Quest["ID"] to get the values.
* `Check if all objects are collected` - Constantly checks if the amount of objects collected is equal to the objects that have to be collected. In case if you set the quest to `Completed`.
* `Update quest title` - Updates the `Title` of the quest.
* `Update quest title` - Updates the `Description` of the quest.
* `Update quest title` - Updates the `Status` of the quest.
* `Update quest can be abandoned` - Updates `CanAbandon` of the quest.
* `(Collect) Add 1 collectable` - Add 1 to the objects to collect in the `Collected` variable

### Conditions
* `Quest exists` - Checks if a quest exists given its `ID`
* `(Collect) Is quest completed?` - Checks if the `Status` of the quest is equal to `Completed`.
