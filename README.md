<div align="center">
  <h1>The Fab Store</h1>
  <p>E-commerce temático dos Beatles com carrinho global, animações de scroll e filtros dinâmicos.</p>

  <a href="https://ricardosampaio.dev/the-fab-store/">Ver projeto ao vivo</a>
</div>

<br />

<div align="center">
  <img src="https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/GSAP-88CE02?logo=greensock&logoColor=white" />
</div>

<br />

## Preview

<img width="1538" height="865" alt="Captura de tela 2026-05-08 153727" src="https://github.com/user-attachments/assets/ffc7ae7a-95cf-4894-94ea-53ccfb9fb03e" />



## Features

- **Carrinho global** — Estado centralizado com Context API, acessível de qualquer componente
- **Animações de scroll** — Revelações e transições controladas pelo GSAP ScrollTrigger
- **Filtros dinâmicos** — Navegação por categorias com atualização instantânea
- **Checkout interativo** — Modal de finalização com resumo do pedido
- **Design responsivo** — Layout adaptado para desktop e mobile

## Estrutura

```
src/
├── assets/             # Imagens, ícones e fontes
├── components/         # Header, Main, Footer, SidebarCart, CheckoutModal
├── context/            # CartContext (estado global do carrinho)
├── utils/              # Dados dos produtos
├── App.js              # Layout e integração GSAP
└── index.css           # Estilos globais e variáveis
```

## Rodando localmente

```bash
git clone https://github.com/ricardosampaiodev/the-fab-store.git
cd the-fab-store
npm install
npm start
```
