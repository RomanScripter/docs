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
        ['panel'] = {
            ['main'] = {
                ['title'] = "Concessionária",
                ['amount'] = "R$ ${amount}",
                ['welcome'] = "Seja bem vindo(a), ${nickname}",
                ['know more'] = "Saiba mais",
                ['your money'] = "Seu dinheiro,",
                ['description'] = "As melhores marcas, os melhores modelos e condições de pagamento imperdíveis! Estamos esperando por você!",
            },

            ['vehicles'] = {
                ['stock disponible'] = "Estoque disp. ${stock}",
                ['acceleration'] = "Aceleração",
                ['vehicle list'] = "Lista de Veículos",
                ['no has stock'] = "Sem estoque",
                ['test drive'] = "Teste Drive",
                ['max speed'] = "Velocidade máxima",
                ['search'] = "Procurar...",
                ['brakes'] = "Freio",
                ['trunk'] = "Porta Malas",
                ['price'] = "R$ ${price}",
                ['cash'] = "C$ ${cash}",
                ['buy'] = "Comprar",
            },

            ['test drive'] = {
                ['title'] = "Test Drive",
                ['description'] = "Restam ${seconds} segundo(s)."
            }
        },

        ['messages'] = {
            ['main'] = {
                ['This category is empty'] = "Não há veículos nessa categoria!",
                ['this category is blocked only vips'] = "Essa categoria é permitida apenas para VIPS.",
            },

            ['test drive'] = {
                ['started'] = "Você iniciou o teste drive do veículo.",
                ['finalized'] = "Você finalizou o teste drive do veículo.",
                ['vehicle exit'] = "Você saiu do veículo e perdeu o Test Drive!",
                ['player wasted'] = "Você morreu e perdeu o Test Drive do veículo!"
            }
        }
    }
};
```
{% endcode %}

Para adicionar outro idioma, basta copiar tudo que está entre **\['pt-BR'] = {** e **}**, e altere o pt-BR para a língua que deseja, mais exemplos abaixo.

{% code lineNumbers="true" %}
```lua
language = {
    ['pt-BR'] = {
        ['panel'] = {
            ['main'] = {
                ['title'] = "Concessionária",
                ['amount'] = "R$ ${amount}",
                ['welcome'] = "Seja bem vindo(a), ${nickname}",
                ['know more'] = "Saiba mais",
                ['your money'] = "Seu dinheiro,",
                ['description'] = "As melhores marcas, os melhores modelos e condições de pagamento imperdíveis! Estamos esperando por você!",
            },

            ['vehicles'] = {
                ['stock disponible'] = "Estoque disp. ${stock}",
                ['acceleration'] = "Aceleração",
                ['vehicle list'] = "Lista de Veículos",
                ['no has stock'] = "Sem estoque",
                ['test drive'] = "Teste Drive",
                ['max speed'] = "Velocidade máxima",
                ['search'] = "Procurar...",
                ['brakes'] = "Freio",
                ['trunk'] = "Porta Malas",
                ['price'] = "R$ ${price}",
                ['cash'] = "C$ ${cash}",
                ['buy'] = "Comprar",
            },

            ['test drive'] = {
                ['title'] = "Test Drive",
                ['description'] = "Restam ${seconds} segundo(s)."
            }
        },

        ['messages'] = {
            ['main'] = {
                ['This category is empty'] = "Não há veículos nessa categoria!",
                ['this category is blocked only vips'] = "Essa categoria é permitida apenas para VIPS.",
            },

            ['test drive'] = {
                ['started'] = "Você iniciou o teste drive do veículo.",
                ['finalized'] = "Você finalizou o teste drive do veículo.",
                ['vehicle exit'] = "Você saiu do veículo e perdeu o Test Drive!",
                ['player wasted'] = "Você morreu e perdeu o Test Drive do veículo!"
            }
        }
    },
    ['en-US'] = {
        ['panel'] = {
            ['main'] = {
                ['title'] = "Concessionária",
                ['amount'] = "R$ ${amount}",
                ['welcome'] = "Seja bem vindo(a), ${nickname}",
                ['know more'] = "Saiba mais",
                ['your money'] = "Seu dinheiro,",
                ['description'] = "As melhores marcas, os melhores modelos e condições de pagamento imperdíveis! Estamos esperando por você!",
            },

            ['vehicles'] = {
                ['stock disponible'] = "Estoque disp. ${stock}",
                ['acceleration'] = "Aceleração",
                ['vehicle list'] = "Lista de Veículos",
                ['no has stock'] = "Sem estoque",
                ['test drive'] = "Teste Drive",
                ['max speed'] = "Velocidade máxima",
                ['search'] = "Procurar...",
                ['brakes'] = "Freio",
                ['trunk'] = "Porta Malas",
                ['price'] = "R$ ${price}",
                ['cash'] = "C$ ${cash}",
                ['buy'] = "Comprar",
            },

            ['test drive'] = {
                ['title'] = "Test Drive",
                ['description'] = "Restam ${seconds} segundo(s)."
            }
        },

        ['messages'] = {
            ['main'] = {
                ['This category is empty'] = "Não há veículos nessa categoria!",
                ['this category is blocked only vips'] = "Essa categoria é permitida apenas para VIPS.",
            },

            ['test drive'] = {
                ['started'] = "Você iniciou o teste drive do veículo.",
                ['finalized'] = "Você finalizou o teste drive do veículo.",
                ['vehicle exit'] = "Você saiu do veículo e perdeu o Test Drive!",
                ['player wasted'] = "Você morreu e perdeu o Test Drive do veículo!"
            }
        }
    }
};
```
{% endcode %}

Como no exemplo acima, eu copiei a tradução em português, mudei o **pt-BR** para **en-US** e fiz as minhas traduções, e para aplicar no sistema, eu irei em **system** e procuro a opção **\['language'] = "pt-BR"** e mudo o **"pt-BR"** para **"en-US"** (ou para o seu idioma desejado).&#x20;
