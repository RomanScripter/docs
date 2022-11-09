# 🌍 Idiomas

## :question: Para que serve essa funcionalidade?

> Funcionalidade criada para deixar a usabilidade do sistema em outros países viável, sendo assim, possibilitando o uso do sistema para as pessoas que não falam português, e sim outro idioma.

## :cloud: Como posso adicionar outro idioma?

> Para adicionar outro idioma é muito simples, irei dar o exemplo para adicionar algum outro idioma no Paintball, porém, caso queira adicionar outro idioma em algum outro sistema da **Roman Store**, basta seguir os mesmos passos.

{% hint style="warning" %}
Caso não entenda, abra um [Ticket](ticket.md) e tire suas dúvidas com nossa equipe de suporte.
{% endhint %}

{% code lineNumbers="true" %}
```lua
language = {
    ['pt-BR'] = {
        ['hud round winner'] = "VENCEU A RODADA",

        ['scoreboard title'] = "SCOREBOARD",

        ['spectate info'] = "Você está espectando o(a) #FFFF00${nickname} \n#FFFFFFPara alterar o jogador, pressione #FFFF00< #FFFFFFou #FFFF00>",

        ['waiting team exit'] = "PRESSIONE #7D50EF${key} #FFFFFFPARA SAIR",
        ['waiting team remaining'] = "Restam ${seconds} segundo(s) para iniciar.",
        ['waiting team waiting players'] = "Aguardando jogadores",

        ['buy time open'] = "Pressione \"${key}\" para abrir a loja de itens.",
        ['buy time close'] = "FECHAR",
        ['buy time title'] = "LOJA DE ARMAMENTOS",
        ['buy time buyed item'] = "Você comprou um item na loja.",

        ['select team open'] = "Pressione \"${key}\" para abrir a seleção de times.",        
        ['select team exit team'] = "Pressione #7D50EF${key} #ffffffpara sair do time.",
        ['select team close match'] = "Já está acontecendo uma partida aqui, volte mais tarde!",
        ['select team selected team'] = "Você selecionou um time!",
        ['select team panel join team'] = "ENTRAR",
    }
};
```
{% endcode %}

Para adicionar outro idioma, basta copiar tudo que está entre **\['pt-BR'] = {** e **}**, e altere o pt-BR para a língua que deseja, mais exemplos abaixo.

{% code lineNumbers="true" %}
```lua
language = {
    ['pt-BR'] = {
        ['hud round winner'] = "VENCEU A RODADA",

        ['scoreboard title'] = "SCOREBOARD",

        ['spectate info'] = "Você está espectando o(a) #FFFF00${nickname}\n#FFFFFFPara alterar o jogador, pressione #FFFF00< #FFFFFFou #FFFF00>",

        ['waiting team exit'] = "PRESSIONE #7D50EF${key} #FFFFFFPARA SAIR",
        ['waiting team remaining'] = "Restam ${seconds} segundo(s) para iniciar.",
        ['waiting team waiting players'] = "Aguardando jogadores",

        ['buy time open'] = "Pressione \"${key}\" para abrir a loja de itens.",
        ['buy time close'] = "FECHAR",
        ['buy time title'] = "LOJA DE ARMAMENTOS",
        ['buy time buyed item'] = "Você comprou um item na loja.",

        ['select team open'] = "Pressione \"${key}\" para abrir a seleção de times.",        
        ['select team exit team'] = "Pressione #7D50EF${key} #ffffffpara sair do time.",
        ['select team close match'] = "Já está acontecendo uma partida aqui, volte mais tarde!",
        ['select team selected team'] = "Você selecionou um time!",
        ['select team panel join team'] = "ENTRAR",
    },

    ['en-US'] = {
        ['hud round winner'] = "WON THE ROUND",

        ['scoreboard title'] = "SCOREBOARD",

        ['spectate info'] = "You are viewer of #FFFF00${nickname}\n#FFFFFFTo change the player, press #FFFF00< #FFFFFFto #FFFF00>",

        ['waiting team exit'] = "PRESS #7D50EF${key} #FFFFFFTO EXIT",
        ['waiting team remaining'] = "${seconds} second(s) left to start.",
        ['waiting team waiting players'] = "Waiting for players",

        ['buy time open'] = "Press \"${key}\" to open the item shop.",
        ['buy time close'] = "CLOSE",
        ['buy time title'] = "WEAPONS STORE",
        ['buy time buyed item'] = "You purchased an item in the store.",

        ['select team open'] = "Press \"${key}\" to open the team selection.",        
        ['select team exit team'] = "Press #7D50EF${key} #ffffff to leave the team.",
        ['select team close match'] = "There's already a game going on here, come back later!",
        ['select team selected team'] = "You have selected a team!",
        ['select team panel join team'] = "JOIN",
    }
};
```
{% endcode %}

Como no exemplo acima, eu copiei a tradução em português, mudei o **pt-BR** para **en-US** e fiz as minhas traduções, e para aplicar no sistema, eu irei em **system** e procuro a opção **\['language'] = "pt-BR"** e mudo o **"pt-BR"** para **"en-US"** (ou para o seu idioma desejado).&#x20;
