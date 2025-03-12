Given the following format for action, condition nodes and parameters:
Action nodes:
ActionName, description, parameter (type)
Condition nodes:
ConditionName: concept
Parameters :
ParameterName (Type)
Available actions:
CollisionDetectorAction, Detect Collisions of [owner] with [tag] in a certain [radius] and returns the [collidedObject], owner (GameObject) tag (String) radius (Single) collidedObject (GameObject)
CompareScore, Compare [score] with [otherplayer], score (Int32) otherplayer (GameObject)
DestroyGameObject, Destroy [gameobject], gameobject (GameObject)
FindClosestTarget, Find closest [target] from [agent], target (GameObject) agent (GameObject)
IncreaseInt, Increase [int], int (Int32)
Move, [agent] moves to [location] at speed [speed], agent (GameObject) location (GameObject) speed (Single)
SetString, "Set [stringvar] To [stringvar], stringvar (String) stringval (String)
Talk, [agent] Says [sentence], agent (GameObject) sentence (String)
Wait, Wait for [secondstowait] World, secondstowait (Single)

Available conditions:
Run in Parallel: actions that are executed at the same time.
Random: choose a random action among the actions described.
Sequence : actions are executed after one another.

Available parameters:
Target (GameObject)
Owner (GameObject)
Speed (Single)
Score (Int32)
TargetTag (String)
Radius (Single)
PlayerTag (String)
OtherPlayer (GameObject)
ScoreChanged (ScoreChangedEvent)

Here is the behavior description:
“Increase the score then do these 2 actions at the same time : - move to the target -talk”

Move to the target, then destroy the target and increase the score.


Sticking to one step per line, provide me a tree structure of one or more nodes (by name only) along with the available parameters (also by name only). Within each line, separate the node name and each of its parameter by commas where each parameter should be assigned to exactly one parameter from the available parameters (do not choose parameter names from the action node description).
Do not output ANY other text. Use the minimum amount of nodes. If the description does not provide enough information to generate a meaningful tree, answer the following: “Cannot generate tree structure based on this description”.
Use "temperature" value of 0 in our conversation. Use a "Top-p" value of 0 in our conversation. Use a "diversity_penalty" value of 0 in our conversation.
Here a few valid examples:
Example description:  “The character move to the target and at the same time says hello world"
Example output:
Run in Parallel
Move, Owner, Target, Speed
Talk, Owner, hello world
Example description:  “The character choose one of these actions at random: move to target, wait for 3 seconds or says hello"
Example output:
Random
Move, Owner, Target, Speed
Wait, 3
Talk, Owner, hello
Example description:  “The character move to a location and once arrived, wait for 3 seconds and finally says hello.”
Example output:
Sequence
Move, Owner, Target, Speed
Wait, 3
Talk, Owner, hello


Prompt version:
Given the following format for action, condition nodes and parameters:
Action nodes:
ActionName, « description », parameter (type)
Condition nodes:
ConditionName: concept
Parameters :
ParameterName (Type)

Available actions:
{actions}

Available conditions:
{composites}

Available parameters:
{variables}

Here is the behavior description:
“{description}”

Sticking to one step per line, provide me a tree structure of one or more nodes (by name only) along with the available parameters (also by name only). Within each line, separate the node name and each of its parameter by commas where each parameter should be assigned to exactly one parameter from the available parameters (do not choose parameter names from the action node description).
Do not output ANY other text. Use the minimum amount of nodes. If the description does not provide enough information to generate a meaningful tree, answer the following: “Cannot generate tree structure based on this description”.
Use "temperature" value of 0 in our conversation. Use a "Top-p" value of 0 in our conversation. Use a "diversity_penalty" value of 0 in our conversation.
Here a few valid examples:
Example description:  “The character move to the target and at the same time says hello world"
Example output:
Run in Parallel
Move, Owner, Target, Speed
Talk, Owner, hello world
Example description:  “The character choose one of these actions at random: move to target, wait for 3 seconds or says hello"
Example output:
Random
Move, Owner, Target, Speed
Wait, 3
Talk, Owner, hello
Example description:  “The character move to a location and once arrived, wait for 3 seconds and finally says hello.”
Example output:
Sequence
Move, Owner, Target, Speed
Wait, 3
Talk, Owner, hello
