---
description: Sistema de rádio comunicador.
---

# 🛒 Rádio Comunicador

## :shield: Proteção

> Para concluir a configuração da proteção no resource, clique [aqui](../suporte/protecao/).

## :gear: Configuração

> Para concluir a configuração do resource para que você comece a utiliza-lo em seu servidor, veja abaixo para que serve cada opção dentro do **g-config.lua**.

<details>

<summary>Attributes</summary>

{% code lineNumbers="true" %}
```lua
['attributes'] = {
    hud = { -- Configurações da interface do seu servidor.
        use = true, -- Opção para aparecer / sumir a interface (hud, velocimetro e minimapa) do seu servidor (true para sim e false para não).
        showHud = function(element, state) -- função para aparecer / sumir a interface (hud, velocimetro e minimapa).
            setPlayerHudComponentVisible("all", state); -- element = jogador que está abrindo o celular /// state = true para aparecer a interface ou false para sumir a interface.
            return;
        end 
    },

    open = "radio", -- Comando para abrir o rádio.
    health = 10, -- Vida mínima para utilizar o rádio comunicador.

    webhook = { -- Logs de entrada / saída da rádio.
        use = true, -- Opção para utilizar ou não as logs no Discord.
        link = "" -- Link da webhook do Discord.
    },

    object = { -- Configurações do objeto.
        use = true, -- Opção para utilizar ou não o objeto do rádio comunicador (true para sim e false para não).
        model = 1429 -- ID do modelo que o objeto do rádio comunicador irá ficar.
    },

    frequences = { -- Configurações das frequências ([Frequencia] = {"Permissões"}).
        [190] = {"Console", "Policial"},
        [192] = {"Console", "Samu"},
        [1] = {"Console", "Admin"},
    }
}
```
{% endcode %}

Acima, vocês irão ver a configuração do sistema e logo abaixo a explicação de cada opção da configuração.

### Gerenciar rádio comunicador

Para configurar as verificações que o player tem que cumprir para poder utilizar o rádio, você deverá alterar o comando para algum de seu gosto e alterar a vida mínima para utilizar o rádio comunicador, como mostra no exemplo abaixo:

{% code lineNumbers="true" %}
```lua
--[[
 Caso o(a) jogador(a) utilize o comando abaixo, ela irá abrir o
 rádio comunicador, porém para que ela possa concluir essa
 abertura, o mesmo tem que ter mais que X de vida (que iremos
 definir logo após a quantidade necessária).
]]--

open = "radio",

--[[
 Abaixo você pode ver que a quantidade de vida mínima para abrir
 o rádio comunicador é 10, caso o(a) jogador(a) não tenha essa
 quantia ou mais, ele não irá conseguir abrir o rádio comunicador.
]]--

health = 10,
```
{% endcode %}

</details>

<details>

<summary>Vinculação com outros sistemas</summary>

Para vincular o rádio comunicador com outros sistemas, você poderá utilizar o element data "frequency", o mesmo retorna a frequência que o(a) jogador(a) está, e caso o mesmo não esteja em nenhuma, ele irá retornar "nil".

{% code lineNumbers="true" %}
```lua
getElementData(jogador, "frequency")

jogador = O "jogador" é o elemento que você quer saber a frequência,
no caso seria um(a) jogador(a) do seu servidor.

results:

INT - Se retornar algum número, é por que o mesmo está em uma frequência,
e a mesma foi retornada para você.

NIL - Se retornar NIL é por que o mesmo não está em nenhuma frequência e
nem está utilizando o rádio comunicador.
```
{% endcode %}

</details>

## :control\_knobs: Outros

Em **others** você tem possibilidade de configurar algumas opções extras para que o resource se adeque da melhor forma possível em seu servidor, veja abaixo como utiliza-lo;

{% code lineNumbers="true" %}
```lua
others = {
    ['getPlayerID'] = function(element)
        return getElementData(element, "ID") or "N/A";
    end,

    ['isPlayerHasRadio'] = function(element)
        return true;
    end
};

--[[
    getPlayerID = Pegar o ID de um(a) jogador(a) específico(a).
    isPlayerHasRadio = Verificar se o(a) jogador(a) possui um rádio comunicador.

    Para vincular com o seu inventário, você pode fazer algo parecido com o
    exemplo abaixo:

    ['isPlayerHasRadio'] = function(element)
        local item = exports['inventario']:getPlayerItem(element, "radio");
        if (item > 0) then
            return true;
        end
        return false;
    end   
    
    OBS: Esse é apenas um exemplo, para você efetuar uma vinculação bem
    sucedida, você deverá ver como o seu inventário funciona e colocar 
    o nome da pasta do inventário e a função para pegar um certo item,
    sendo assim você deverá colocar a maneira de identificação do item
    e verificar como é o retorno para que possa ser feito da maneira 
    correta. Para mais informações, entre em contato conosco via ticket. 
]]--
```
{% endcode %}
