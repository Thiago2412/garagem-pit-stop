<p align="center">
  <img src="assets/logo.webp" alt="Logo da Garagem Pit Stop – Oficina Automotiva" width="420">
</p>

<h1 align="center">Sistema de Controle de Estoque</h1>

<p align="center">
  Aplicação web para uma oficina mecânica controlar peças, entradas e saídas, compras e lucro,<br>
  com acesso por login e níveis de permissão.
</p>

<p align="center">
  <img alt="HTML5" src="https://img.shields.io/badge/HTML5-e34f26?logo=html5&logoColor=white">
  <img alt="CSS3" src="https://img.shields.io/badge/CSS3-1572b6?logo=css3&logoColor=white">
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-f7df1e?logo=javascript&logoColor=black">
  <img alt="Responsivo" src="https://img.shields.io/badge/Layout-responsivo-red">
  <img alt="Sem framework" src="https://img.shields.io/badge/Sem-framework-black">
</p>

<p align="center">
  <a href="https://thiago2412.github.io/garagem-pit-stop/"><strong>▶ Testar online</strong></a>
</p>

---

## Sobre o projeto

A **Garagem Pit Stop** é uma oficina automotiva fictícia. O sistema foi criado para resolver um problema comum em oficinas pequenas: saber quais peças existem no estoque, o que está acabando, o que precisa ser comprado e quanto o estoque vale, sem depender de caderno ou planilha solta.

Tudo roda direto no navegador, em uma única página, **sem servidor e sem bibliotecas externas**. Os dados ficam salvos no próprio navegador, e o sistema já vem com um catálogo de exemplo para ser testado na hora.

| 145 | 20 | 7 | 0 |
|:---:|:---:|:---:|:---:|
| peças no catálogo de exemplo | categorias com código automático | telas no sistema | bibliotecas externas |

## Como testar

**Online:** acesse o link do [GitHub Pages](https://thiago2412.github.io/garagem-pit-stop/).

**Localmente:** baixe o repositório e abra o arquivo `index.html` no navegador. Não precisa instalar nada.

> **Login de demonstração**
> Usuário: `thiago` · Senha: `123456` (super admin)

## Telas

### Dashboard
Visão geral do estoque, com indicadores, gráfico de movimentação e alertas de estoque baixo.

![Dashboard](assets/screenshots/dashboard.webp)

### Login
Acesso com usuário e senha e aviso quando algo está errado.

![Login](assets/screenshots/login.webp)

### Estoque
Cadastro com preenchimento automático e busca por nome, código ou categoria.

![Estoque](assets/screenshots/estoque.webp)

### Entradas e saídas
Os dois registros na mesma tela, com histórico único.

![Entradas e saídas](assets/screenshots/entradas-saidas.webp)

### Relatórios
O que comprar hoje, peças paradas e lucro por peça.

![Relatórios](assets/screenshots/relatorios.webp)

### Categorias
Prefixo de código, quantidade de produtos e valor em estoque de cada categoria.

![Categorias](assets/screenshots/categorias.webp)

### Administradores
Contas numeradas, quem cadastrou cada uma e, para o super admin, os botões de promover e excluir com confirmação.

![Administradores](assets/screenshots/administradores.webp)

### Versão para celular
O layout se adapta à tela: o menu vira um botão ☰, os cartões ficam em uma coluna e aparecem as **Ações rápidas**, que só existem no celular.

<p>
  <img src="assets/screenshots/mobile-inicio.webp" alt="Tela inicial no celular" width="260">
  <img src="assets/screenshots/mobile-indicadores.webp" alt="Indicadores no celular" width="260">
</p>

## Funcionalidades

- 🔐 **Login e níveis de acesso:** entrada com usuário e senha, aviso de erro e senha guardada como hash. Super admins podem excluir contas e promover administradores.
- 📊 **Dashboard:** indicadores de estoque, valor de custo e de venda, lucro potencial, gráfico dos últimos 5 meses e últimas movimentações.
- 📦 **Cadastro de produtos:** código gerado pela categoria (ex.: `FRE001`). Se o produto já existe, a quantidade é somada em vez de duplicar.
- 🔄 **Entradas e saídas:** registro de compras (fornecedor/nota) e de uso em serviços (OS/mecânico), com histórico de quem registrou cada uma.
- 🗂 **Categorias:** criação de categorias com prefixo automático. Bloqueia nomes repetidos, mesmo com acento ou maiúsculas diferentes.
- 🛒 **Relatórios:** lista de compras com sugestão de quantidade e custo, peças paradas há 6 meses e lucro por peça.
- 🔔 **Alertas:** contador de produtos abaixo do estoque mínimo sempre visível no topo da tela.
- ⚙️ **Backup e segurança:** exportação dos dados em JSON (sem as senhas). Restaurar os dados de exemplo exige a senha de um super admin.

## Como foi feito

| Item | Detalhes |
|---|---|
| **Linguagens** | HTML5, CSS3 e JavaScript (ES2020+), sem framework e sem bibliotecas |
| **Interface** | Telas montadas com template strings e redesenhadas por uma função `render()` a cada mudança de dados |
| **Layout** | CSS Grid e Flexbox, variáveis CSS para as cores e media queries para tablet e celular |
| **Gráfico** | Desenhado em SVG pelo próprio código, sem biblioteca de gráficos |
| **Dados** | `localStorage`, com migração automática de dados de versões antigas e plano B na memória quando o navegador bloqueia o armazenamento |
| **Senhas** | Guardadas como hash, nunca em texto. A exportação em JSON não inclui as senhas |
| **Segurança** | Todo texto digitado é escapado antes de aparecer na tela, para evitar injeção de HTML |
| **Acessibilidade** | Foco visível no teclado, textos alternativos, avisos com `role="alert"` e respeito à opção de reduzir animações |

## Limitações e próximos passos

Por ser um projeto sem servidor, os dados e as contas ficam salvos **só no navegador de quem usa**. O login protege a interface, mas não substitui uma autenticação feita no servidor.

- [ ] Ligar o sistema a um banco de dados online (como Firebase ou Supabase) com login de verdade
- [ ] Editar produtos já cadastrados e trocar a própria senha
- [ ] Importar backup em JSON e exportar o estoque em CSV para Excel
- [ ] Filtro por período no histórico e nos relatórios
- [ ] Instalar como aplicativo no celular (PWA)

## Autor

**Henrique Petrone Bertacini**
Projeto de portfólio · Novembro de 2026

## Licença

Distribuído sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
