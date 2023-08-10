---
description: Sistema de venda de armas, vinculável a qualquer inventário.
---

# 🛒 Venda de Armas

## :shield: Proteção

> Para concluir a configuração da proteção no resource de Venda de Armas, clique [aqui](../suporte/protecao/).

## :gear: Configuração

> Para concluir a configuração do resource para que você comece a utiliza-lo em seu servidor, veja abaixo para que serve cada opção dentro do **g-config.lua**.

<details>

<summary>Webhook</summary>

{% code lineNumbers="true" %}
```lua
['webhook'] = "",
```
{% endcode %}

A opção mostrada acima é utilizada para enviar notificações das armas que foram fabricadas atráves do sistema de Fabricação de Armas.&#x20;

* **webhook:** Link do webhook do Discord.

</details>

<details>

<summary>Configs</summary>

{% code lineNumbers="true" %}
```lua
system = {
    ['open'] = "b", 
    ['distance'] = 7,

    ['price'] = {
        min = 5000,
        max = 200000
    },

    ['weapons-permitted'] = {
        [22] = true, -- Colt 45
        [24] = true, -- Deagle
        [25] = true, -- Shotgun
        [28] = true, -- Uzi
        [29] = true, -- MP5
        [32] = true, -- Tec-9
        [30] = true, -- AK-47
        [31] = true, -- M4A1
        [34] = true -- Sniper
    }
};
```
{% endcode %}

A opção mostrada acima é utilizada para configurar o sistema de vendas de armas com mais precisão, e deixar da forma que você deseja.

* **open:** Tecla que você irá utilizar para abrir o painel.
* **distance:** Distância que o vendedor pode ficar do comprador da arma.
* **price:** Preço mínimo e preço máximo que uma arma pode ser vendida.
* **weapons-permitted:** Armas permitidas para vendas.\
  \- Use esse modelo: **\[ID da ARMA] = true,**

</details>

## :control\_knobs: Outros

{% code lineNumbers="true" %}
```lua
others = {
    ['managerHud'] = function(element, state)
        return setPlayerHudComponentVisible("all", state);
    end,

    ['givePlayerWeapon'] = function(element, id, ammo)
        return giveWeapon(element, id, ammo);
    end,

    ['getPlayerID'] = function(element)
        return getElementData(element, "ID") or "N/A";
    end,
    
    ['takeMoney'] = function(element, amount)
        return takePlayerMoney(element, amount);
    end,

    ['getMoney'] = function(element)
        return getPlayerMoney(element);
    end
};
```
{% endcode %}

> Em **others** você tem possibilidade de configurar algumas opções extras para que o resource se adeque da melhor forma possível em seu servidor (alterar apenas as informações que estão após o return).

* **managerHud:** Retirar a sua HUD e o RADAR da tela ao iniciar uma partida, não é obrigatório, porém a tela do jogador fica mais "clean".
* **givePlayerWeapon:** Função para dar a arma para o jogador após a fabricação (caso você tenha inventário e as suas armas for por ele, você deverá vincula-lo aqui.
* **getPlayerID:** Função para pegar o ID do jogador.
* **takeMoney:** Função para retirar uma quantia de dinheiro do jogador.
* **getMoney:** Função para pegar a quantidade de dinheiro do jogador.
