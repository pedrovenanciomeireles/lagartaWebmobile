# lagartaWebmobile
**Pedro Henrique Venancio Meireles 10747973**
### Uma explicação inicial sobre o processo de ideação.
  O processo de ideação do meu projeto teve como objetivo principal desenvolver uma solução voltada para a comunidade, que fosse prática, funcional e possível de implementar dentro do prazo proposto. Durante a etapa inicial de planejamento, considerei duas ideias principais.
A primeira proposta era a criação de um site para divulgar os serviços de instalação e manutenção realizados pelo pai de um colega, como instalação de televisores, cabeamento residencial, antenas e internet. A ideia era ajudar na divulgação do trabalho e facilitar o contato com possíveis clientes.
A segunda proposta, que foi a escolhida, consiste na criação de um site para divulgação e venda de velas produzidas pelo meu tio. Após analisar as duas opções, entendi que o modelo de venda de produtos poderia gerar um impacto maior na comunidade e oferecer mais possibilidades de desenvolvimento, como a organização de um catálogo e a simulação de um sistema de compras. Por isso, optei por essa ideia, buscando criar uma plataforma simples e acessível para fortalecer a presença digital do negócio.

### Uma explicação sobre o caráter extensionista

O projeto possui caráter extensionista por estabelecer uma conexão direta entre o conhecimento acadêmico e uma demanda real da comunidade. A proposta será desenvolvida em parceria com a empresa do meu tio, que atua no ramo de fabricação e venda de velas há anos, vivenciando diariamente os desafios operacionais e comerciais do negócio.
A criação do site tem como objetivo auxiliar nos processos de venda, automatizando etapas fundamentais que atualmente consomem tempo e tornam as tarefas diárias mais desgastantes. Desse modo, a solução buscará otimizar a rotina da empresa, melhorar a organização dos pedidos e contribuir para o fortalecimento da presença digital do empreendimento.
Além disso, o projeto permitirá a participação ativa do empresário na avaliação e sugestão de melhorias, possibilitando ajustes conforme as necessidades reais do negócio. Essa interação reforça meu compromisso social, profissional e ético ao aplicar conhecimentos técnicos em benefício direto da comunidade e do desenvolvimento local.

# Projeto Alvaluz

Projeto de um site institucional/e-commerce para uma loja de velas chamado **Alvaluz**, desenvolvido com **HTML, CSS e JavaScript**.

---

## Estrutura do Projeto

```bash
📦 alvaluz
 ┣ 📜 index.html
 ┣ 📜 carrinho.html
 ┣ 📜 login.html
 ┣ 📜 cadastro.html
 ┣ 📜 style.css
 ┣ 📜 script.js
 ┣ 🖼️ logo.png
 ┣ 🖼️ fabrica.webp
```

---

# 🧱 1. HTML (Estrutura)

O arquivo `index.html` define toda a estrutura do site.

---

## Header

### `#headerNav`

* Botão menu (☰)
* Logo
* Campo de busca
* Ícones (carrinho + usuário)

### `#headerLinks`

* Home
* Catálogo
* Contato (WhatsApp)

---

## Aside (Menu Lateral)

* Menu oculto inicialmente
* Abre ao clicar no botão ☰
* Contém:

  * Home
  * Velas (submenu)
  * Contato

---

## Submenu "Velas"

Categorias:

* Clássicas
* Aromatizantes
* Religiosas

---

## Banner

Imagem principal do site:

```html
<section id="banner">
  <img src="fabrica.webp">
</section>
```

---

## Outras Seções

* `#categorias` → futuras categorias
* `#carrosel` → futuro slider
* `#sobre` → produtos ou informações

---

## Footer

* Contatos
* Redes sociais
* Estrutura expandida em colunas (Logo, Links Úteis, Atendimento, Redes Sociais com ícones interativos)

---

## Novas Páginas Adicionadas

* **Carrinho de Compras (`carrinho.html`)**: Lista de produtos escolhidos, controle de quantidade, remoção de itens e painel lateral de resumo do pedido (subtotal, frete, total).
* **Login (`login.html`)**: Formulário centralizado em cartão para acesso de usuário (e-mail e senha).
* **Cadastro (`cadastro.html`)**: Formulário para registro de novos usuários (nome completo, e-mail, senha e confirmação).

---

# 🎨 2. CSS (Estilização)

Arquivo: `style.css`

---

## Reset Global

```css
* {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}
```

---

## Header com Gradiente

```css
header {
  background: radial-gradient(circle,
    rgba(187, 216, 237, 1) 0%,
    rgba(131, 205, 235, 1) 100%);
}
```

---

## Layout com Flexbox

```css
#headerNav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

## Campo de Busca

```css
input {
  width: 31rem;
  border-radius: 10px;
  border: none;
}
```

---

## Menu Lateral

```css
aside {
  transform: translateX(-100%);
  transition: transform 0.3s ease;
}

aside.ativo {
  transform: translateX(0);
}
```

---

## Submenu Animado

```css
#catalogoToggle {
  max-height: 0;
  overflow: hidden;
}

#catalogoToggle.ativo {
  max-height: 300px;
}
```

---

## Efeitos Hover

```css
.headerLink:hover,
.icon:hover {
  color: #fff;
}
```

---

## Ícones

* Biblioteca: Flaticon

```css
.icon {
  font-size: 1.3rem;
}
```

---

## Animação do Ícone

```css
#iconeVelas.ativo {
  transform: rotate(90deg);
}
```

---

## Estilos Adicionais (Novas Implementações)

* **Banner Responsivo**: Utilização de `height: 50vh` e `object-fit: cover` para cobrir a área sem distorcer a imagem.
* **Layout do Carrinho**: Distribuição em `flex: 2` (lista de itens) e `flex: 1` (resumo do pedido).
* **Formulários (Login/Cadastro)**: Fundo `f4f7f6` com cartões brancos com `box-shadow` suave, inputs responsivos com ícones internos.
* **Footer**: Fundo `rgb(38, 98, 141)`, fontes claras, ícones com efeitos de `hover` e elevação (`transform: translateY`).

---

# ⚙️ 3. JavaScript (Interatividade)

Arquivo: `script.js`

---

## Inicialização

```js
document.addEventListener("DOMContentLoaded", function () {
```

Garante que o DOM esteja carregado antes de executar.

---

## Seleção de Elementos

```js
const item = document.getElementById("itemCatalogo");
const menu = document.getElementById("catalogoToggle");
const icone = document.getElementById("iconeVelas");

const aside = document.querySelector("aside");
const botaoAside = document.getElementById("botaoAside");
const botaoFecharAside = document.getElementById("botaoFecharAside");
```

---

## Toggle do Submenu

```js
item.addEventListener("click", function (e) {
  e.preventDefault();

  if (menu.style.maxHeight && menu.style.maxHeight !== "0px") {
    menu.style.maxHeight = "0px";
    icone.classList.remove("ativo");
  } else {
    menu.style.maxHeight = menu.scrollHeight + "px";
    icone.classList.add("ativo");
  }
});
```

### O que faz:

* Abre/fecha o submenu
* Anima altura dinamicamente
* Rotaciona o ícone

---

## Abrir Menu Lateral

```js
botaoAside.addEventListener("click", function () {
  aside.classList.add("ativo");
});
```

---

## Fechar Menu Lateral

```js
botaoFecharAside.addEventListener("click", function () {
  aside.classList.remove("ativo");
});
```

---

# Funcionalidades

* Menu lateral animado
* Submenu expansível
* Rotação de ícone
* Layout moderno
* Estrutura pronta para e-commerce
* **Interface do Carrinho de Compras visualmente completa**
* **Sistema de Autenticação visual (Telas de Login e Cadastro)**

---

# Fluxo de Uso

| Ação              | Resultado         |
| ----------------- | ----------------- |
| Clique no ☰       | Abre menu lateral |
| Clique no ❌       | Fecha menu        |
| Clique em "Velas" | Abre submenu      |
| Clique novamente  | Fecha submenu     |
| Clique em 🛒       | Abre página Carrinho |
| Clique em 👤       | Abre página Login |

---

# Melhorias Futuras

* Responsividade mobile
* Carrossel funcional
* Sistema de busca
* Backend (produtos reais)
* Carrinho de compras (funcionalidade lógica de adicionar itens)

---

# Tecnologias Utilizadas

* HTML5
* CSS3
* JavaScript
* Flaticon Icons (Solid, Regular, Bold e Brands)

---

# Autor

Desenvolvido por Pedro Henrique Venancio Meireles 10747973.
