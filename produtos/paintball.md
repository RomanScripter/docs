---
description: >-
  Paintall é um minigame de FPS disputado entre duas equipes, onde quem matar a
  outra equipe primeiro ganha.
---

# 🔫 Paintball

## :shield: Proteção

> Para concluir a configuração da proteção no resource de Paintball, clique [aqui](../suporte/protecao/).

## :gear: Configuração

> Para concluir a configuração do resource para que você comece a utiliza-lo em seu servidor, veja abaixo para que serve cada opção dentro do **g-config.lua**.

<details>

<summary>Linguagens</summary>

{% code lineNumbers="true" %}
```lua
['language'] = "pt-BR",
```
{% endcode %}

A opção "language" dentro do resource, serve para você definir o idioma principal do sistema, veja mais em :earth\_africa: [**Idiomas**](../suporte/idiomas.md)**.**

</details>

<details>

<summary>Binds</summary>

{% code lineNumbers="true" %}
```lua
['open-shop'] = "B", -- Abrir SHOP de itens na partida.
['team-choose'] = "E", -- Abrir seleção de times.
['team-exit'] = "F7", -- Sair de um time.
['open-scoreboard'] = "F1", -- Abrir SCOREBOARD da partida.
```
{% endcode %}

As opções mostradas acima, são para alterar as teclas que você quer utilizar para tais funcionalidades. Na ordem correta, acima você deverá alterar as teclas para;&#x20;

* **open-shop:** Abrir o SHOP de itens para comprar colete, armas e outros utensílios.
* **team-choose:** Abrir painel para selecionar o seu time (BLUE ou PINK).
* **team-exit:** Sair do time selecionado na pré-partida.**open-scoreboard:** Abrir o SCOREBOARD com os dados da partida (kills, dinheiro & mortes).

</details>

<details>

<summary>Posições</summary>

{% code lineNumbers="true" %}
```lua
['positions'] = {
    [1] = {pos = {1045.781, -953.056, 42.630}, int = 0, dim = 0, color = {115, 0, 0, 255}, blip = {use = true, icon = 18}},
},
```
{% endcode %}

A opção "positions", possibilita a criação de locais para que a escolha dos times de Paintball seja feita. Também é possível alterar outras coisas, veja mais sobre abaixo.

* **pos:** Posição X, Y e Z de onde o painel irá ficar no mundo.
* **int:** Interior que o painel irá ficar.
* **dim:** Dimensão que o painel irá ficar.
* **color:** Cor e visibilidade do marker (RGBA).
* **blip \[use]:** Opção para usar ou não o BLIP (utilize **true** para utilizar e **false** para desabilitar).
* **blip \[icon]:** Ícone que irá ficar no radar, para ver mais ícones clique [aqui](https://wiki.multitheftauto.com/wiki/Radar\_Blips).

</details>

<details>

<summary>Headshot</summary>

{% code lineNumbers="true" %}
```lua
['headshot'] = { 
    -- Headshot dentro da partida.
    ['actived'] = true,
    ['damage'] = 100,
 },

['headshotOutMatch'] = { 
    -- Headshot fora da partida.
    ['actived'] = true,
    ['damage'] = 100,
 },
```
{% endcode %}

Sistema de headshot próprio do sistema, o sistema é utilizado dentro e fora do sistema, você deverá parar de utilizar o seu sistema comum de headshot e utilizar o do sistema próprio.

* **headshot \[actived]:** Opção para usar ou não o Headshot na partida (utilize **true** para utilizar e **false** para desabilitar).

</details>
