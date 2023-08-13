---
description: Sistema de médico completo.
---

# 🛒 Samu

## :shield: Proteção

> Para concluir a configuração da proteção no resource, clique [aqui](../suporte/protecao/).

## :gear: Configuração

> Para concluir a configuração do resource para que você comece a utiliza-lo em seu servidor, veja abaixo para que serve cada opção dentro do **g-config.lua**.

<details>

<summary>Interação</summary>

{% code lineNumbers="true" %}
```lua
interaction = {
    use = true, -- Opção para utilizar ou não o sistema de interação.
    
    resuscitation = {
        animation = {"MEDIC", "CPR"}, -- Animação que o médico ao fazer a reanimação.
        health = 20, -- Vida que o jogador terá ao ser reanimado.
        time = 8 -- Tempo para a reanimação ser realizada (em segundos).
    },

    reward = {
        min = 5000, -- Mínimo que o SAMU pode ganhar por reanimação.
        max = 10000 -- Máximo que o SAMU pode ganhar por reanimação.
    }
}
```
{% endcode %}

Acima, vocês irão ver a configuração do sistema de interação do próprio samu, caso você não queira utilizar, só desabilita-lo.&#x20;

### **Como habilitar ou desabilitar essa opção?**

Para mudar o estado de uso do sistema de interação do samu você deverá utilizar **true** para **sim** ou **false** para **não,** como mostra no exemplo abaixo:

{% code lineNumbers="true" %}
```lua
--[[
 Se a opção abaixo for sim (true), você irá passar a 
 utilizar um sistema de interação do próprio sistema, 
 caso a opção abaixo for não (false) você irá passar a utilizar
 um sistema fornecido por você (sistema próprio de interação, que não
 seja do sistema de SAMU).
]]--


-- Para habilitar o painel de interação do próprio SAMU:
use = true,

-- Para habilitar o painel de interação do seu servidor:
use = false;
```
{% endcode %}

### Utilizando um sistema de interação próprio

Caso você opte por utilizar um sistema de interação próprio, você deverá vincula-lo com o nosso sistema de samu para que não haja problemas ao utilizar o sistema, abaixo você verá como vincular o seu sistema de interação ao nosso sistema de samu passo a passo.

<pre class="language-lua" data-line-numbers><code class="lang-lua"><strong>-- Reviver outros jogadores:
</strong><strong>triggerEvent("EMS >> Interaction >> Player resuscitation", player, jogador);
</strong><strong>
</strong><strong>-- Curar outros jogadores:
</strong>triggerEvent("EMS >> Interaction >> Player tratament", player, jogador);

--[[
    "EMS >> Interaction >> Player resuscitation" = Evento utilizado.
    "EMS >> Interaction >> Player tratament" = Evento utilizado.
    jogador = Jogador que irá receber a ressurreição.
    player = Jogador que está clicando no outro.
]]-- 
</code></pre>



Caso decida continuar utilizando o nosso sistema de interações, você deverá configurar as outras opções de configurações, abaixo irei listar para que serve cada opção e como configurar-lá.

{% code lineNumbers="true" %}
```lua
resuscitation = {
    animation = {"MEDIC", "CPR"},
    health = 20,
    time = 8
},

--[[
    animation: "animation" é o nome da animação (bloco e animação)
    que o(a) jogador(a) irá executar ao iniciar a ressurreição 
    da vítima.
    
    health: "health" é a vida que a vítima irá ter após ser
    ressuscitada.
    
    time: "time" é o tempo que o(a) jogador(a) irá demorar
    para ressuscitar a vítima.
]]--

reward = {
    min = 5000, -- Mínimo que o SAMU pode ganhar por reanimação.
    max = 10000 -- Máximo que o SAMU pode ganhar por reanimação.
}

--[[
    min: "min" é a quantidade mínima de dinheiro que o(a) jogador(a)
    irá ganhar por cada ressurreição efetuada.
    
    max: "max" é a quantidade máxima de dinheiro que o(a) jogador(a)
    irá ganhar por cada ressurreição efetuada.
    
    obs: o sistema pega a quantida de mínima e a quantidade máxima
    e pega um valor aleatório entre esses dois números, sendo assim,
    gerando o valor do pagamento pela ressurreição feita pelo(a) 
    jogador(a).
]]--
```
{% endcode %}

</details>

<details>

<summary>Maca</summary>

<pre class="language-lua" data-line-numbers><code class="lang-lua"><strong>hospital_bed = {
</strong>    permissions = {"Console", "Admin"}, -- Permissões para criar / deletar macas.
    objectId = 1997, -- ID do objeto da MACA.
    heal = 5000, -- Valor para se curar sozinho (somente na maca).

    commands = {
        create = "criarmaca", -- Comando para criar macas.
        delete = "deletarmaca" -- Comando para deletar macas.
    },
},
</code></pre>

Acima está a configuração do sistema de maca do próprio samu, veja abaixo como configurá-lo.

{% code lineNumbers="true" %}
```lua
permissions = {"Console", "Admin"},

--[[
    permissions: "permissions" são as permissõs para gerenciar
    as macas criadas, podendo criar e deletar as macas.
]]--

objectId = 1997,
heal = 5000,

--[[
    objectId: "objectId" é o ID do objeto que você irá utilizar
    como maca do samu.
    
    heal: "heal" é o preço para se curar apenas se deitando na 
    maca, sem nenhuma ajuda de médicos.
]]--

commands = {
    create = "criarmaca",
    delete = "deletarmaca"
},

--[[
    create: "create" é o comando para criar novas macas no servidor.
    delete: "delete" é o comando para deletar as macas próximas,
    macas que já foram criadas e estão no servidor.
]]--
```
{% endcode %}

</details>

<details>

<summary>Morte</summary>

{% code lineNumbers="true" %}
```lua
wasted = {
    key = "E", -- Tecla para chamar os médicos.
    blip = 41, -- Ícone do BLIP para chamados.
    time = 500, -- Segundos para você reviver (em segundos).
    animation = {"CRACK", "crckdeth2"}, -- Animação que o jogador irá fazer ao morrer.
    
    finalize = {
        use = true,  -- Opção para ser finalizado direto caso não haja nenhum médico online (true para sim e false para não).
        count = 2 -- Quantidade mínima de médicos para não ser finalizado direto.
    },

    sound = {
        use = true, -- Opção para ativar ou desativar a música ao morrer (true para sim e false para não).

        link = "https://www.youtube.com/watch?v=bS1Nf0syICc", -- Som da música no YouTube.
        title = "Gucci Mane, Bruno Mars, Kodak Black - Wake Up In The Sky", -- Título da música.
        volume = 20, -- Volume da música.
    }
}
```
{% endcode %}

Acima está a configuração do sistema de maca do próprio samu, veja abaixo como configurá-lo.

{% code lineNumbers="true" %}
```lua
key = "E",
blip = 41,
time = 500,
animation = {"CRACK", "crckdeth2"},

--[[
    key: "key" é a tecla para chamar os médicos online
    quando a vítima estiver morta.
    
    blip: "blip" é o ID do blip que será mostrado ao chamar
    o médico.
    
    time: "time" é o tempo que a vítima terá que esperar para
    ser revivido ou apenas se matar novamente.
    
    animation: "animation" é o bloco e o nome da animação que 
    o médico irá que fazer ao reanimar a vítima
]]--

finalize = {
    use = true,
    count = 2
},

--[[
     use: "use" é a opção para usar ou não a opção de ser finalizado
     automaticamente em casos de não haver médicos suficientes on-line
     
     true = sim
     false = não
     
     para deixar ativado, utilize:
     use = true,
     
     para deixar desativado, utilize:
     use = false,
     
     count: "count" é a quantidade de médicos que deverá estar
     on-line para que a vítima não seja finalizado automaticamente
]]--

sound = {
   use = true,

   link = "https://www.youtube.com/watch?v=bS1Nf0syICc",
   title = "Gucci Mane, Bruno Mars, Kodak Black - Wake Up In The Sky",
   volume = 20,
}

--[[
     use: "use" é a opção para usar ou não a opção de usar ou não
     músicas no painel que a vítima irá ver após morrer.
     
     true = sim
     false = não
     
     para deixar ativado, utilize:
     use = true,
     
     para deixar desativado, utilize:
     use = false,
     
     link: "link" é a url da música no YouTube
     title: "title" é o título da música que irá aparecer
     para as vítimas que morrerem.
]]--
```
{% endcode %}

</details>

## :control\_knobs: Outros

Em **others** você tem possibilidade de configurar algumas opções extras para que o resource se adeque da melhor forma possível em seu servidor, veja abaixo como utiliza-lo;

{% code lineNumbers="true" %}
```lua
others = {
    ['managerHud'] = function(element, state)
        return setPlayerHudComponentVisible("all", state);
    end,

    ['getPlayerID'] = function(element)
        return getElementData(element, "ID") or "N/A";
    end,

    ['notifyMedic'] = function(element)
        return outputChatBox("\n[SAMU] #F8F8F8Um novo chamado realizado! foi marcado em seu GPS!", element, 255, 0, 0, true);
    end,

    ['attachedBlip'] = function(element, icon, visibleTo)
        return createBlipAttachedTo(element, icon, 2, 255, 255, 255, 255, 0, 300, visibleTo);
    end,

    -- DINHEIRO

    ['getMoney'] = function(element)
        return getPlayerMoney(element);
    end,

    ['takeMoney'] = function(element, amount)
        return takePlayerMoney(element, amount);
    end,

    ['giveMoney'] = function(element, amount)
        return givePlayerMoney(element, amount);
    end
};

--[[
    managerHud: Função para habilitar e desabilitar a hud,
    caso não queira utilizar, basta deixa-la como o exemplo abaixo:
    
    ['managerHud'] = function(element, state)
        return;
    end,
    
    getPlayerID: Pegar o ID do(a) jogador(a) desejado.
    notifyMedic: Mensagem de notificação que irá aparecer para o médico.
    attachedBlip: Blip que irá ficar na vítima que chamou o médico.
    getMoney: Quantidade de dinheiro que o(a) jogador(a) possui.
    takeMoney: Retirar uma quantia de dinheiro do(a) jogador(a).
    giveMoney: Adicionar uma quantia de dinheiro do(a) jogador(a).
]]--
```
{% endcode %}
