# script
mais 1 script
-- Configurações do script
local players = {} -- Tabela para armazenar os jogadores

-- Função para desenhar a vida e o time dos jogadores
function drawPlayerInfo(player)
    if player.isBehindWall then
        -- Define a cor para o time vermelho
        love.graphics.setColor(1, 0, 0) -- RGB para vermelho
        -- Desenha a quantidade de vida
        love.graphics.print("Vida: " .. player.health, player.x, player.y - 20)
        -- Desenha o time
        love.graphics.print("Time: " .. player.team, player.x, player.y)
    end
end

-- Função principal para atualizar e desenhar
function love.draw()
    for _, player in ipairs(players) do
        drawPlayerInfo(player)
    end
end

-- Exemplo de adição de jogadores (substitua com a lógica real do seu jogo)
table.insert(players, { x = 100, y = 150, health = 80, team = "Time A", isBehindWall = true })
table.insert(players, { x = 200, y = 150, health = 50, team = "Time B", isBehindWall = false })
