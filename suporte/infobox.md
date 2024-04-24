# 🎲 Infobox

{% hint style="warning" %}
Depois de ler toda a página e ainda não estiver entendo, abra um **⚒️** [**Ticket**](broken-reference) para que nossa equipe auxilie você.
{% endhint %}

## :question: O que é infobox?

> Infobox é uma caixa de notificação para o jogador, onde você envia alguns avisos para o jogador através do Infobox.

## :cloud: Como alterar o Infobox do meu resource?

> Para alterar o infobox padrão do nosso resource para o seu, você deverá acessar o **`g-config.lua`** de seu resource e seguir os passos abaixo.

## :desktop: O que devo alterar?

> Para alterar o seu infobox e não ter nenhum risco de erro, primeiramente altere as informações da tabela **`notify`** e coloque os tipos de notificação que seu infobox tem.&#x20;

> Aqui, você deverá alterar somente o que está depois de **`= ""`,** exemplo:&#x20;

{% code lineNumbers="true" %}
```lua
--[[
    ANTES DA ALTERAÇÃO
--]]

notify = {
    ['warning'] = "warning",
    ['success'] = "success",
    ['error'] = "error",
    ['info'] = "info"
};

--[[
    DEPOIS DA ALTERAÇÃO
--]]

notify = {
    ['warning'] = "aviso",
    ['success'] = "sucesso",
    ['error'] = "erro",
    ['info'] = "info"
};

-- O que está entre [''], nunca deverá ser alterado!
```
{% endcode %}

> E para fazer a sua vinculação corretamente, você deverá adicionar ou alterar o **`exports`**/**`triggers`**.

{% code lineNumbers="true" %}
```lua
--[[
    A alteração deverá ser feita dessa forma:
]]--

geral = {
    ['sNotify'] = function(element, message, type)
        return exports['dx-messages']:addBox(element, message, notify[type]); -- Coloque as informações que você precisa depois do return.
    end,

    ['cNotify'] = function(element, message, type)
        return triggerEvent("addBox", element, message, notify[type]);  -- Coloque as informações que você precisa depois do return.
    end
};

--[[
- exports['nome-do-resource']:nomeDaFunção(parâmetros do seu infobox);

- Element = jogador que receberá a mensagem.
- Message = Mensagem que o jogador receberá.
- Type = Tipo da notificação (utilize o type dessa forma: notify[type]).
]]--
```
{% endcode %}

