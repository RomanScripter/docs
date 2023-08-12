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

</details>
