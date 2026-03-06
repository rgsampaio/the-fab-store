# 🍏 The Fab Store

<img width="1502" height="843" alt="image" src="https://github.com/user-attachments/assets/8b23b2ab-001c-4002-bbff-4ba96c6d6e64" />


> 🎸 **Acesse a loja rodando ao vivo:** https://ricardosampaio.dev/the-fab-store

## 💡 Sobre o Projeto
A The Fab Store não é só mais um "projeto de curso". É um e-commerce temático dedicado ao legado dos Beatles, construído do zero no Figma, até chegar no código, para simular os desafios reais que enfrentamos no mercado de Front-end. 

O meu objetivo aqui foi ir muito além de montar uma interface estática. Eu queria focar no que realmente converte e segura um usuário em uma loja: **performance, gerenciamento de estado limpo e uma experiência imersiva e impecável no celular.**

## 🛠️ Como as coisas funcionam por baixo do panos

Para fazer a loja rodar lisa, tomei algumas decisões de arquitetura cruciais:

* **React.js:** A base de tudo, focando em componentização real e reaproveitamento de interface.
* **Context API (O cérebro do carrinho):** Em vez de passar os dados do carrinho de mão em mão, criei um estado global (`CartContext`). Qualquer botão "Comprar" do site conversa instantaneamente com a barra lateral, somando itens e calculando totais de forma centralizada.
* **GSAP (GreenSock):** O CSS puro não dava conta da imersão que eu queria. Trouxe o GSAP para assumir o controle do *smooth scroll* e das animações baseadas na rolagem, garantindo uma fluidez visual.

## 🥊 As Batalhas que Venci

Fazer o código rodar no `localhost` é fácil. O desafio foi domar a performance em produção. Aqui estão os principais problemas de engenharia que resolvi:

**1. Orquestra Visual e ScrollTrigger**
Criar a revelação da logo na seção de "Legado" exigiu sincronizar escala, opacidade e posição estritamente atrelados à rolagem do usuário. Usei o `ScrollTrigger` do GSAP para calcular o ponto exato de interseção na tela, garantindo que a animação pesada rodasse de forma suave, sem engasgar o *scroll* da página ou causar quedas de *framerate*.

**2. A Guerra do Carrinho no Mobile (GSAP vs. Touch Nativo)**
O motor de scroll do GSAP é incrível, mas no celular, ele costuma "sequestrar" a tela. Quando o usuário abria o carrinho, a rolagem da lista de produtos travava. 
* **A solução:** Criei uma lógica no React (via `useEffect`) que monitora a abertura da Sidebar e **pausa ativamente** o motor do GSAP (`smoother.paused()`). Juntando isso com a regra `overscroll-behavior: contain` no CSS, liberei o toque nativo do aparelho e o carrinho voltou a rodar liso.

**3. Engenharia de Performance e Diagnóstico (PageSpeed Insights)**
E-commerce lento não vende. Foquei em otimizar o carregamento da aplicação para dispositivos móveis, priorizando a experiência do usuário real acima de métricas de vaidade. Implementei uma série de melhorias recomendadas pelo Lighthouse para garantir estabilidade e velocidade:

* **Otimização do Caminho Crítico:** Movi as fontes do Google Fonts para o HTML com `preconnect` e utilizei `font-display: swap` na fonte customizada (*Bootle*), eliminando o atraso visual (FOIT) e permitindo que o conteúdo seja lido instantaneamente.
* **Estratégia de Cache e Assets:** Comprimi imagens pesadas para o formato `.webp` (reduzindo o payload em mais de 80%) e configurei um arquivo `vercel.json` com regras de cache agressivas. Isso garante que, em acessos recorrentes, a loja carregue quase instantaneamente a partir do dispositivo do usuário.

## 🚀 Como rodar na sua máquina

A arquitetura não é uma caixa preta. Se quiser ver o código funcionando localmente:

```bash
# Clone este repositório
git clone https://github.com/ricardosampaiodev/the-fab-store.git

# Entre na pasta
cd the-fab-store

# Instale as dependências
npm install

# Rode o servidor
npm start
