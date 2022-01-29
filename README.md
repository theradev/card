This is the first prototype.  The next part will involve the player creating cards on the fly.

label draw:

  show poutine ardent

  t "Ask a computer program to repeat your last action."

  hide poutine ardent

  $ d20roll = renpy.random.randint(1, 5)

  if d20roll == 1:

      show poutine neutral

      t "You are an engineer."

      hide poutine neutral

  else:

      if d20roll == 2:

          show poutine neutral

          t "Make an exhaustive list of everything you might do and do the last thing on the list."

          hide poutine neutral

      else:

            if d20roll == 3:

              show poutine neutral

              t "Shuffling music like cards!"

              hide poutine neutral

            else:

                if d20roll == 4:

                  show poutine neutral

                  t "Altar of fire / Burning bridges."

                  "(Get rid of low-priority tasks.)"

                  hide poutine neutral

                else:

                  if d20roll == 5:

                      show poutine neutral

                      t "Don’t be frightened to display your talents."

                      hide poutine neutral

  menu:

    "Draw a card.":
        jump draw

    "Go back.":
        jump main_zero


label exit:

    show poutine think

    "Don't throw in the towel!"

    show poutine neutral

    "Whatever I can do for you.."


return

/
/

"I've been thinking about changing my name."

# The phrase in the brackets is the text that the game will display to prompt 
# the player to enter the name they've chosen.

    $ player_name = renpy.input("What is your name, Magical Boy?")

    $ player_name = player_name.strip()
# The .strip() instruction removes any extra spaces the player 
# may have typed by accident.

#  If the player can't be bothered to choose a name, then we
#  choose a suitable one for them:
    if player_name == "":
        $ player_name="Shuji"

# And get a nostalgic sigh from Seasons of Sakura fans!
    
# Now the other characters in the game can greet the player.
  
    e "Pleased to meet you, %(player_name)s!"
