NOTES

How to make Kraft Mac & Cheese:
- Go to a kitchen
    - Look for a stove and sink
    - If the kitchen does not have a stove and a sink, go to a different kitchen
    - Check if the stove and sink work
    - If either the stove or the sink doesn’t work, go to a different kitchen
- Look for the materials
    - Materials: medium sauce pan, cooking spoon, colander, measuring cup, a knife, dish soap, and a sponge
    - If you do not have the materials, go buy materials
    - Clean the dishes with the dish soap, sink, and sponge
    - If you run out of dish soap before the dishes are clean, go buy dish soap
    - If the sponge stops working before the dishes are clean, go buy a new sponge
- Look for the ingredients
    - Ingredients: original Kraft mac & cheese box, butter sticks, and milk
    - If you have the ingredients, check their expiration dates
    - If any ingredients are expired, go buy ingredients
    - If the ingredients are fresh, check that you have 4 tablespoons of butter and 1/4 cups of milk
    - If you do not, go buy ingredients
- Using the measuring cup, sink, and empty sauce pan, pour 6 cups of water into the sauce pan
- Place the sauce pan onto a working burner that is not already occupied or turned on
- Turn the corresponding burner on medium
- Let the water cook until the water is rapidly boiling
- Put the pasta in the boiling water, stir briefly with the cooking spoon, and set a timer for 9 minutes
- Stir the pasta every 2 minutes with the cooking spoon
- When the timer goes off, turn the burner off, and place the sauce pan and colander into the empty sink
- Pour the contents of the sauce pan into the colander over the sink
- Pour the contents of the colander into the empty sauce pan
- Measure 1/4 cups of milk with the measuring cup and pour into the pan
- Measure 4 tablespoons of butter from the butter stick wrapper, cut the butter with your knife, remove the butter from the wrapper, and place the butter into the pan
- Remove the cheese packet from the Kraft box, tear it open, and pour the cheese into the pan
- Stir the pasta until the mixture is uniform
- Serve

PROGRAM fixKraftMacAndCheese

// define objects
```
kitchen  
    stove  
        burner  
            temp  
            heat  
        timer  
    sink  
        faucet  
            condition  
        content  
```
```
materials  
    dishes  
        mediumPan  
            content  
        cookSpoon  
        colander  
            content  
        measureCup  
            content  
        knife  
    dishSoap  
        content  
    sponge  
        condition  
```
```
ingredients  
    kraftBox  
        pasta  
        cheese  
    butterStick  
        amount  
    milk  
        amount  
```
// deploy
```
while (kitchen#burner#heat === false || sink#faucet#condition === false) {  
    chooseLocation(kitchen)  
        test(stove, sink)  
    }  
gather(materials, ingredients, kitchen) {  
    have(materials)  
    wash(dishes, materials#dishSoap, materials#sponge)  
    have(ingredients)  
    fresh(ingredients)  
    enough(ingredients, materials#measureCup)  
}  
cook(kitchen, materials, ingredients) {  
    addWaterToPan(kitchen#sink, materials#mediumPan, materials#measureCup)  
    placePanOnStove(kitchen#stove, materials#mediumPan)  
    turnBurnerOn(kitchen#stove)  
    boilWater(kitchen#stove, materials#mediumPan)  
    openKraftBox(ingredients#kraftBox)  
        removeCheesePouch(kraftBox)  
    addPastaToPan(ingredients#kraftBox#pasta, materials#mediumPan, materials#cookSpoon)  
        stir(mediumPan, cookSpoon)  
    startTimer(kitchen#stove, materials#mediumPan, materials#cookSpoon)  
        every 2 minutes {  
            stir(mediumPan, cookSpoon)  
        }  
    turnBurnerOff(kitchen#stove)  
    movePanToSink(materials#mediumPan, kitchen#sink)  
    moveColanderToSink(materials#colander, kitchen#sink)  
    pourPanToColander(materials#mediumPan, materials#colander)  
    pourColanderToPan(materials#mediumPan, materials#colander)  
    measureMilk(ingredients#milk, materials#measureCup)  
    addMilkToPan(ingredients#milk, materials#mediumPan)  
    measureButter(ingredients#butterStick, materials#knife)  
    addButterToPan(ingredients#butterStick, materials#mediumPan)  
    openCheesePouch(ingredients#kraftBox#cheesePouch)  
    addCheeseToPan(ingredients#kraftBox#cheesePouch, materials#mediumPan)  
    stirUntilUniform(materials#mediumPan, materials#cookSpoon)  
    serve(materials#mediumPan, materials#cookSpoon)  
}  
```