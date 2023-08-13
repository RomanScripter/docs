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
