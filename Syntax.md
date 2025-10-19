# Syntax

## Popups

One of the first syntax commands I have ever made is a very important one is geode's offical documentation
The 
```
FLAlertLayer::create(
    "Title",
    "Text",
    "Button"
)->show();

```

but in GGD I changed it to be more simpler, even though this is already very simple

```
NewAlert{
  "Title",
  "Text",
  "Button"
}
```

I also made it so that it is easy to make a disclaimer popup right as you load into the main menu and/or when you download the mod.
```
DisclaimerAlert{
  "Disclaimer Text"
}
```
This is where the disclaimer's title is set to "Disclaimer" and the button is "agree" (and you cannot get a popup for the TOS and the PrPo, because then, why would you already have geode?)

## Buttons
One of the most NEEDED UI elements, the button!
Usally you need to type in all of this:
```
bool MyLayer::init() {
    

    auto spr = ButtonSprite::create("Button");

    auto btn = CCMenuItemSpriteExtra::create(
        spr, this, nullptr
    );

    
    menu->addChild(btn);

   
}

```
But instead for GGD it is
```
CreateButton("Name", Place, ID, Enabled on default?)
```
If you want to make a main menu button, you need to type in
```
MMnewButton("Name", Filename, ID)
```

## Events
So, the 2nd MOST IMPORTANT thing in modding, events.
For most things in GD, such as CCTextInputNode, GD and Cocos2d-x use a delegate-based event system
As an alternative to this system, Geode introduces events.
These events are still too complex, so we are making a whole MD file about it. (This is line SIX SEVENNNN)
It is events.md, please check it out :)

## Fields
Kinda like variables, fields are varibles. One is can be connected to how many times a player has jumped
Here is a example in C++:
```
int totalJumps = 0;

class $modify(PlayerObject) {
    void pushButton(PlayerButton button) {

        totalJumps++;
        PlayerObject::pushButton(button);
    }
};
```
This is not even the best way to store jumps, but I made a better way to do this:
```
Var <Name Here> = VALUE
```
And to store stuff like how many jumps a player makes you can do:
```
Var totalJumps = 0
waitfor pushButton(space):
    Var totalJumps = totalJumps+1
    log.info("the player has jumped {totalJumps}")
    return
```
