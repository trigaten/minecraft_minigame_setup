# minecraft_minigame_setup


# init
/scoreboard objectives add round dummy "round"

/scoreboard objectives add count_down dummy "count_down"

/scoreboard objectives add health health "health"

/scoreboard objectives setdisplay belowName health

/scoreboard objectives add zombie_count dummy "zombie_count"

/setblock 16 15 52 minecraft:redstone_block destroy



# infinite
/execute if score d count_down matches 1.. run scoreboard players remove d count_down 1

# start chain
/scoreboard players reset d round

# start new round chain
/title @p title [{"text":"Round ", "color":"red"}, {"score":{"name":"d","objective":"round"},"color":"red", "italic":true}]
