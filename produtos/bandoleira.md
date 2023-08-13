---
description: Sistema de bandoleira.
---

# 🛒 Bandoleira

## :shield: Proteção

> Para concluir a configuração da proteção no resource, clique [aqui](../suporte/protecao/).

## :gear: Configuração

> Para concluir a configuração do resource para que você comece a utiliza-lo em seu servidor, veja abaixo para que serve cada opção dentro do **g-config.lua**.

<details>

<summary>Geral</summary>

{% code lineNumbers="true" %}
```lua
['manager'] = { -- Opção para usar ou não a bandoleira (opção individual).
    use = true, -- Opção para deixar esse comando ativo ou não (true para sim e false para não).
    command = "bandoleira", -- Comando para mostrar / esconder a bandoleira.
    permissions = {"Console", "Admin"} -- Permissões para utilizar o comando para mostrar / esconder a bandoleira.
},

['weapon_ammo'] = { -- Opção para a arma aparecer somente quando haver munições.
    use = false, -- Opção para ativar ou não (true == sim // false == não).
    min = 1 -- Mínimo de munição que deverá estar na arma
}
```
{% endcode %}

Acima temos a configuração do sistema de bandoleira, veja logo abaixo para configura-lo corretamente.

{% code lineNumbers="true" %}
```lua
['manager'] = {
    use = true,
    command = "bandoleira",
    permissions = {"Console", "Admin"}
},

--[[
     use: "use" é a opção para usar ou não a opção de utilizar
     um comando para esconder a bandoleira (apenas do(a) jogador(a))
     ou não.
     
     true = sim
     false = não
     
     para deixar ativado, utilize:
     use = true,
     
     para deixar desativado, utilize:
     use = false,
     
     command: Comando que será utilizado para alterar o
     estado de visualização da bandoleira (individual).
     
     permissions: Permissões para utilizar o comando de
     alterar o estado de visualização da bandoleira.
]]--

['weapon_ammo'] = {
    use = false,
    min = 1
}

--[[
     use: "use" é a opção para usar ou não a opção de alterar
     a visibilidade da arma conforme a quantidade de munições
     das armas do(a) jogador(a).
     
     true = sim
     false = não
     
     para deixar ativado, utilize:
     use = true,
     
     para deixar desativado, utilize:
     use = false,
     
     min: Mínimo de munições para que a arma apareça no corpo do(a)
     jogador(a).
]]--
```
{% endcode %}

</details>

<details>

<summary>Vinculação</summary>

Para vincular o seu sistema de inventário com o nosso sistema, basta utilizar as informações abaixo como base:\


{% code lineNumbers="true" %}
```lua
--[[
    Para utilizar, basta inserir a função abaixo nas funções do
    seu inventário referente ao "useItem".

    Função que deverá ser utilizado ao pegar / remover armas
    utilizando o inventário.
]]--

exports['[RS]Bandoleira']:refreshBandoleira(element);

--[[
    [RS]Bandoleira: Nome da pasta do script.
    element: Jogador(a) que utilizou ou removeu a arma.
    
    A função deverá ser utilizada cada vez que uma arma do inventário
    for pega ou retirada da mão do jogador.
]]--
```
{% endcode %}

</details>
