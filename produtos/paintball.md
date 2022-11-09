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
['open-shop'] = "B",
['team-choose'] = "E",
['team-exit'] = "F7",
['open-scoreboard'] = "F1",
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
* **headshot \[damage]:** Dano que o tiro na cabeça irá dar ao jogador.

<!---->

* **headshotOutMatch \[actived]:** Opção para usar ou não o Headshot fora da partida (utilize **true** para utilizar e **false** para desabilitar).
* **headshotOutMatch \[damage]:** Dano que o tiro na cabeça irá dar ao jogador.

</details>

<details>

<summary>Partida</summary>

{% code lineNumbers="true" %}
```lua
['match-configs'] = {
    ['main_weapon'] = 23,

    ['team'] = {
        ['time_wait'] = 10,
        ['max_members'] = 5,
        ['start_members'] = 4,
        ['friendly_fire'] = false,
    },

    ['coins'] = {
        ['i_dead'] = 800,
        ['not_died'] = 800,
        ['start_match'] = 1500,
        ['kill_player'] = 2500,
    },

    ['rounds'] = {
        ['buy_timer'] = 15,
        ['max_rounds'] = 5,
        ['match_timer'] = 3,
    },

    ['shop'] = {
        ['ak'] = {['name'] = 'ASSAULT RIFLE', ['id'] = 31, ['price'] = 3100},
        ['shotgun'] = {['name'] = 'PUMP SHOTGUN', ['id'] = 25, ['price'] = 2000},
        ['grenade'] = {['name'] = 'GRENADE', ['id'] = 16, ['price'] = 500},
        ['molotov'] = {['name'] = 'MOLOTOV', ['id'] = 18, ['price'] = 400},
        ['sniper'] = {['name'] = 'SNIPER RIFLE', ['id'] = 34, ['price'] = 4750},
        ['armor'] = {['name'] = 'ARMOR', ['id'] = 0, ['price'] = 1000},
        ['smg'] = {['name'] = 'SMG', ['id'] = 29, ['price'] = 1500}
    }
},
```
{% endcode %}

Configurações da partida de Paintball, veja melhor abaixo todas as configurações.

* **main\_weapon:** Arma principal que o jogador terá em todas as partidas (recomendado colocar uma pistol).

<!---->

* **team \[time\_wait]:** Tempo de espera para completar os times.
* **team \[max\_members]:** Máximo de membros que cada time pode ter.
* **team \[start\_members]:** Mínimo de membros que cada time precisa ter para iniciar uma partida.
* **team \[friendly\_fire]:** Opção para usar ou não o Fogo Amigo (dar dano nos membros de seu grupo) na partida (utilize **true** para utilizar e **false** para desabilitar).

<!---->

* **coins \[i\_dead]:** Quantidade de coins que o jogador recebe por morrer em algum round.
* **coins \[not\_died]:** Quantidade de coins que o jogador recebe por não morrer em algum round.
* **coins \[start\_match]:** Quantidade de coins que cada jogador recebe ao iniciar a partida.
* **coins \[kill\_player]:** Quantidade de coins que cada jogador recebe ao matar algum outro jogador na partida.

<!---->

* **rounds \[buy\_timer]:** Tempo que os jogadores tem para comprar os seus itens.
* **rounds \[max\_rounds]:** Máximo de rounds que cada partida vai ter (utilize somente números ímpares nos rounds).
* **rounds \[match\_timer]:** Tempo que cada round vai ter (em **minutos**).

<!---->

* **shop:** Itens de compras que ficarão disponíveis para os jogadores, **não é recomendado** alterar o **NOME** e o **ID** das armas, porém o **PREÇO PODE SER ALTERADO NORMALMENTE**.

</details>

<details>

<summary>Mapa</summary>

{% code lineNumbers="true" %}
```lua
['map-configs'] = {
    ['interior'] = 10,

    ['skins'] = {
        ['blue'] = 0,
        ['pink'] = 1,
    },

    ['positions'] = {
        ['blue'] = {
            [1] = {-976.701, 1074.51, 1344.98, 0, 0, 94.3},
            [2] = {-976.695, 1079.985, 1344.97, 0, 0, 90.1},
            [3] = {-970.619, 1080.018, 1345.012, 0, 0, 92.3},
            [4] = {-970.677, 1074.483, 1345.015, 0, 0, 88.7},
            [5] = {-973.661, 1077.254, 1344.993, 0, 0, 92.3}
        },
    
        ['pink'] = {
            [1] = {-1128.553, 1044.531, 1345.72, 0, 0, 270.9},
            [2] = {-1128.707, 1038.96, 1345.716, 0, 0, 268.5},
            [3] = {-1134.885, 1038.989, 1345.756, 0, 0, 269.3},
            [4] = {-1134.559, 1044.193, 1345.759, 0, 0, 268.8},
            [5] = {-1131.645, 1041.744, 1345.738, 0, 0, 270.8}
        }
    },
}
```
{% endcode %}

Configurações da partida de Paintball, veja melhor abaixo todas as configurações.

* **interior:** Interior que o mapa ficará.

<!---->

* **skins \[blue]:** Skin que o time BLUE usará durante a partida.
* **skin \[pink]:** Skin que o time PINK usará durante a partida.

<!---->

* **positions:** Posição X, Y e Z e Rotação X, Y e Z de onde o player irá spawnar no mapa.
* **positions \[blue]:** Posições de todos os membros que vão spawnar (então se tiver 10 membros, insira 10 indexs com posições diferentes de spawn no mapa do paintball).
* **positions \[pink]:** Posições de todos os membros que vão spawnar (então se tiver 10 membros, insira 10 indexs com posições diferentes de spawn no mapa do paintball).

</details>

## :control\_knobs: Outros

{% code lineNumbers="true" %}
```lua
others = {
    ['managerHud'] = function(element, state)
        setPlayerHudComponentVisible("radar", state);
        return;
    end
};
```
{% endcode %}

> Em **others** você tem possibilidade de retirar a sua HUD e o RADAR da tela ao iniciar uma partida, não é obrigatório, porém a tela do jogador fica mais "clean".
