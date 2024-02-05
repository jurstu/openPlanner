# openPlanner

## observations 

So, the thing is.. There is scrum, kanban boards, git issues, TODO lists and other 100 project planning projects to encapsule everything that could happen within a few months of working on the project.

I'd like this one to be dependency based.

Let's say we need to bake a cake - there are tasks to be finished. 

Let's make a simple TODO:
- make a shopping list
- buy apple, flour, baking powder and some eggs
- cut the apples, mix the ingridients
- put it in the baking tray
- have the oven preheated before that
- bake it for 80 minutes
- take it out and let it cool down
- serve it to guests

There are a few problems with a project like that. First, we had the cake ready, but we needed to wait for the oven to preheat. This was caused by not turning on the oven before, so it could heat-up before it's required. It's also not clear which parts of the plan are made for which people.

Let's redo it:
- (Tom)   - make a shopping list
- (Bill)  - buy apple, flour, baking powder and some eggs
- (Tom)   -     start preheating the oven
- (Mary)  - cut the apples, mix the ingridients
- (Mary)  - put it in the baking tray
-       >>> the oven is already heated up <<<  have the oven preheated before that
- (Mary)  - bake it for 80 minutes
- (Tom)   - take it out and let it cool down
- (Bill)  - serve it to guests



A few things changed:
- There are 3 people doing the cake
- Tom preheats the oven, so Mary doesn't have to wait to put the "mixture" in the oven
- Let's assume only Mary knows how to bake the cake - all other tasks are delegated to Tom and Bill
- Mary may get tired by baking the cake ASAP, Tom and Bill get loaded with tasks of taking out and serving the cake

At this point we have a soolid plan for backing the cake. Right?


So, we could get a few advantages with automatic project planning:
- Mary could get assigned to baking tasks as "the expert" that is only one that can do them
- Tom and Bill may have some downtime in other tasks, meaning they could do some good in cake-backing project
- We could add dependency for backing - a task of preheating the oven
- the same way - cutting apples can have a dependency - BUYING THE APPLES.

This is a simple example, but buying the apples should be done in right time-frame. They can't be bought 2 months prior, they'll go bad. The same way they can't be bought too late.


There are simillar problems in Hardware/Software/Product design.

## how this one could work ? 


Let's say we go into detail for all the tasks. I'll propose a framework for it:
```
{
  "taskName": "make shopping list",
  "requiredSkills": [],
  "designatedPerson": "anyone",
  "dependencies": [],
  "max expected time": ["2h"]
}
{
  "taskName": "buy things from list",
  "requiredSkills": [
    "buing with invoice"
  ],
  "designatedPerson": "anyone",
  "dependencies": ["make shopping list"],
  "max expected time": ["6h"]
}
```

Now, we can see a simple relation between those 2 simple tasks. 

To buy stuff, we first need to know what to buy. 

To compile a system, we first need to know the requirements. 

To design a PCB to fit into the enclosure, we first need to design the enclosure.

It's that simple.

It looks to me like I'm trying to adapt system design knowledge to project planning. Is it a bad idea though?

## profit?

The timeline could be much easier to visualize, due to the fact, that we know more about how the final product depends on tasks and subtasks.

Also, there is a lower possibility to miss a dependency due to the fact, that we can stack them with eachother.

That's all the time I have today (5.02.2024). Thank You








