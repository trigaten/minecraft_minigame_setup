# minecraft_minigame_setup


# init

## initialize scoreboard objectives for keeping track of rounds and other data

### keep track of round
/scoreboard objectives add round dummy "round"

### keep track of time count down between rounds
/scoreboard objectives add count_down dummy "count_down"

### keep track of player healths (for display only purposes)

/scoreboard objectives add health health "health"

### make the player healths display below their names

/scoreboard objectives setdisplay belowName health

### keep track of zombies left to make

/scoreboard objectives add zombie_count dummy "zombie_count"

### setblock command that starts round one

/setblock 16 15 52 minecraft:redstone_block destroy



# infinite

### continually decrement the time-between-rounds counter unless it is < 1

/execute if score d count_down matches 1.. run scoreboard players remove d count_down 1

# start chain
/scoreboard players reset d round

# start new round chain
/title @p title [{"text":"Round ", "color":"red"}, {"score":{"name":"d","objective":"round"},"color":"red", "italic":true}]
