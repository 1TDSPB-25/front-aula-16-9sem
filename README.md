# Aula dia 10/06/2025 - Iniciando com FlexBox
- Flex-Itens


# Exercício para o dia 22/09/2025
# Organização de Páginas

**Objetivo:** mover páginas para a pasta `page/`, corrigir **links relativos** entre as páginas e **replicar o cabeçalho** da página `missao.html` em todas as páginas.  

---

## Regras do exercício
- Trabalhe **somente com HTML**.
- Mantenha nomes de arquivos **em minúsculas**, sem acentos, usando **hífen** quando necessário (ex.: `sobre-a-empresa.html`).
- Não crie nem use arquivos de CSS/JS neste exercício.

---

---

## Tarefa 1 — Mover páginas para `page/`
1. Crie a pasta `page/` na raiz do projeto (se não existir).
2. Mova **todas as páginas secundárias** para `page/` (ex.: `ajuda.html`, `produtos/produtos.html`, `contato.html`, etc.).
3. Deixe **`index.html`** na raiz.

---

## Tarefa 2 — Corrigir links relativos (entre páginas)
Ajuste os `href` dos links para refletir a nova localização dos arquivos.

- **De `index.html` (raiz) → para uma página em `page/`:**
  ```html
  <!-- ANTES -->
  <a href="ajuda.html">Ajuda</a>
  <!-- DEPOIS -->
  <a href="./page/ajuda.html">Ajuda</a>


# Front-End-Design-Engineering / FIAP
```
- Repositório inicial
- Iniciando com comandos básicos
-- git init
-- git commit
-- git config
-- git add
-- git dif
-- git log
-- git show
-- git branch
-- git push
```
## Partindo para um conteúdo mais avançado:
- Manipulando branchs
```
-- git checkout -b
-- git merge

```

# WIREFRAMES

![](./assets/img/wireframe-login-cinza.png)  
 
# Exercício: Página de Login (HTML + CSS externo) com Wireframe

## Objetivo
Construir uma **página de Login** utilizando **HTML semântico** e **CSS externo**, a partir do **wireframe em tons de cinza** fornecido.

- A página deve conter **cabeçalho**, **barra de navegação**, **conteúdo principal** com **formulário de login**, e **rodapé**.
- A barra de navegação deve ter os links: **Home**, **Login**, **Ajuda** (apenas âncoras ou `href="#"` neste exercício).
- O estilo deve ser aplicado **via arquivo CSS externo** (ex.: `styles.css`).

> **Wireframe (referência visual):** veja o arquivo `wireframe-login-cinza.png` neste pacote.

---

## O que é um Wireframe?
Um **wireframe** é um desenho estrutural, em baixa fidelidade, que representa **layout e hierarquia de informações**, **sem cores ou tipografias finais**. Ele serve como **guia visual** para organizar os elementos da página **antes** de aplicar design detalhado.

- **Baixa fidelidade (tons de cinza):** foca na estrutura, não no visual final.
- **Rápido de alterar:** ideal para discutir e revisar a disposição dos elementos.
- **Comunica requisitos:** permite alinhar expectativas do que deve existir na interface.

---

## Partes do Wireframe e o que Implementar

### 1) Cabeçalho (Header)
- Faixa superior da página; contém o **título** ou a **marca** do site.
- Deve usar uma tag semântica `<header>`.
- Pode conter a logo (opcional neste exercício).

### 2) Barra de Navegação (Nav)
- Dentro do cabeçalho (ou logo abaixo), crie uma `<nav>` com **3 links**: `Home`, `Login`, `Ajuda`.
- Utilize uma lista não ordenada `<ul>` com `<li>` e `<a>` para os links.
- A navegação é somente decorativa (sem rotas) neste exercício.

### 3) Conteúdo Principal (Main)
- Use `<main>` para englobar o conteúdo da página.
- No centro, crie um **cartão de login** (container) com:
  - **Título “Login”**
  - **Campo Email** (tipo `email`)
  - **Campo Senha** (tipo `password`)
  - **Checkbox “Lembrar‑me”**
  - Link **“Esqueci minha senha”**
  - **Botão “Entrar”**
  - Um divisor com “ou” e botão secundário **“Criar conta”**

### 4) Rodapé (Footer)
- Use `<footer>` com um texto simples (ex.: `© 2025 Empresa XYZ`).
- O rodapé aparece em todas as páginas do site.

---

## Estrutura HTML sugerida (esqueleto)

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Login • Empresa XYZ</title>
    <link rel="stylesheet" href="./styles.css" />
  </head>
  <body>
    <header class="site-header">
      <div class="container">
        <h1>Empresa XYZ</h1>
        <nav class="site-nav">
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Login</a></li>
            <li><a href="#">Ajuda</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <main class="site-main">
      <section class="login-card">
        <h2>Login</h2>

        <form>
          <label for="email">Email</label>
          <input id="email" name="email" type="email" placeholder="seu@email.com" required />

          <label for="senha">Senha</label>
          <input id="senha" name="senha" type="password" placeholder="••••••••" required />

          <div class="row">
            <label class="checkbox">
              <input type="checkbox" name="remember" />
              <span>Lembrar-me</span>
            </label>

            <a class="link" href="#">Esqueci minha senha</a>
          </div>

          <button type="submit">Entrar</button>

          <div class="divider"><span>ou</span></div>

          <button class="secondary" type="button">Criar conta</button>
        </form>
      </section>
    </main>

    <footer class="site-footer">
      <div class="container">
        <small>© 2025 Empresa XYZ</small>
      </div>
    </footer>
  </body>
</html>
```

---

## CSS externo mínimo (guia rápido)

Crie um arquivo `styles.css` na mesma pasta do `index.html` e importe no `<head>`.
Exemplo simples para aproximar o wireframe (tons de cinza):

```css
:root {
  --bg: #f4f4f4;
  --ink: #222;
  --line: #cfcfcf;
  --panel: #fafafa;
  --panel-2: #e9e9e9;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  background: var(--bg);
  color: var(--ink);
  min-height: 100vh;
  display: grid;
  grid-template-rows: auto 1fr auto;
}

.container { max-width: 1100px; margin: 0 auto; padding: 16px 24px; }

.site-header { background: var(--panel-2); border-bottom: 1px solid var(--line); }
.site-nav ul { display: flex; gap: 24px; list-style: none; margin-top: 8px; }
.site-nav a { text-decoration: none; color: var(--ink); }

.site-main { display: grid; place-items: center; padding: 32px; }
.login-card {
  background: var(--panel);
  width: min(520px, 92vw);
  padding: 28px;
  border: 1px solid var(--line);
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
}

.login-card h2 { margin-bottom: 16px; }
.login-card form { display: grid; gap: 12px; }

input[type="email"],
input[type="password"] {
  border: 1px solid var(--line);
  padding: 12px 14px;
  border-radius: 6px;
  background: white;
}

.row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  margin-top: 4px;
}

.checkbox { display: inline-flex; align-items: center; gap: 8px; }

button {
  border: 1px solid var(--line);
  background: var(--panel-2);
  padding: 12px 16px;
  border-radius: 6px;
  cursor: pointer;
}

button.secondary { background: #efefef; }

.divider {
  position: relative;
  margin: 12px 0;
  height: 1px;
  background: var(--line);
}
.divider span {
  position: absolute;
  left: 50%;
  top: -12px;
  transform: translateX(-50%);
  background: var(--panel);
  padding: 0 8px;
  font-size: 14px;
  color: #666;
}

.site-footer { background: var(--panel-2); border-top: 1px solid var(--line); }
.site-footer .container { padding: 18px 24px; text-align: center; }
```

---

## Requisitos de Entrega (Checklist)

- [ ] Estrutura semântica com `<header>`, `<nav>`, `<main>` e `<footer>`
- [ ] **3 links** na navegação: Home, Login, Ajuda
- [ ] Formulário com **email**, **senha**, **lembrar‑me**, **esqueci a senha**, **entrar**
- [ ] Botão **Criar conta** como ação secundária
- [ ] **CSS externo** aplicado (sem estilos inline)
- [ ] Layout aproximando o **wireframe** fornecido (tons de cinza)
- [ ] HTML válido (verificador W3C recomendado)

---

## Dicas
- Comece pelo HTML sem estilos, validando a estrutura.
- Depois, aplique o CSS externo e ajuste espaçamentos.
- Use variáveis CSS (como no exemplo) para manter tudo em escala de cinza.
- Teste o formulário (sem back‑end) apenas para comportamento visual.

---

## Arquivos deste pacote
- `wireframe-login-cinza.png` — imagem do wireframe em escala de cinza.
- `README.md` — este README com instruções do exercício.

### Exercício 14/10/2025#
# Estilizar a página index com Flex-BOX> 
Layout básico em Flex- Utilize CSS externo.
- Obrigatório FLEX BOX.- Pode adicionar imagens.
- Obrigatório a realização de commits.[Mín=15]
- A entrega é feita aqui no repositório mesmo.
- Pode consultar IA, mas não copiar 100%.
- Utilizar menus diferenciados será um diferencial e ponto extra.



## EXEMPLO ATUAL

# 📌 Entendendo `position: sticky` e o Header Sticky

## 🧱 O que é `position: sticky`

A propriedade **`position: sticky`** é um **modo híbrido entre `relative` e `fixed`**.  
Ela permite que um elemento se comporte normalmente (como `relative`) até que a rolagem da página o leve até um ponto definido — a partir daí, ele **“gruda”** na tela (como `fixed`) enquanto o usuário continua rolando.

---

## ⚙️ Sintaxe básica

```css
header {
  position: sticky;
  top: 0;
  background: white;
}
```

**Explicação:**
- `position: sticky` → ativa o comportamento de “grudar”.
- `top: 0` → indica o ponto onde ele ficará fixo (no topo da tela).
- `background` → garante que o conteúdo abaixo não apareça através do cabeçalho.

---

## 🧩 Funcionamento prático

Imagine que você tem várias seções em uma página longa, e quer que o **título de cada seção** fique fixo no topo enquanto o usuário lê essa parte.  
Quando a próxima seção chega, ela “substitui” a anterior no topo.  
Esse efeito é exatamente o que `position: sticky` faz — **sem precisar de JavaScript**.

---

## 🔄 Diferença entre os tipos de `position`

| Propriedade | Descrição |
|--------------|------------|
| `static` | Padrão. O elemento segue o fluxo normal da página. |
| `relative` | Permite mover o elemento em relação à sua posição original. |
| `absolute` | Fixa o elemento em relação ao primeiro ancestral com `position` definida. |
| `fixed` | Fixa o elemento em relação à **tela** (viewport), mesmo durante a rolagem. |
| `sticky` | Mistura de `relative` e `fixed`: o elemento “gruda” ao atingir o limite definido. |

---

## 🎯 O que é um **Header Sticky**

Um **header sticky** é um cabeçalho (geralmente com menu de navegação) que:
- Rola normalmente com a página até tocar o topo;
- E depois **permanece fixo** no topo da janela de visualização.

---

### 🧠 Exemplo prático

```html
<header>
  <h1>Meu Blog</h1>
  <nav>
    <a href="#">Início</a>
    <a href="#">Artigos</a>
    <a href="#">Contato</a>
  </nav>
</header>

<main>
  <p>Conteúdo extenso aqui...</p>
</main>
```

```css
header {
  position: sticky;
  top: 0;                   /* gruda no topo da tela */
  background: #fff;         /* fundo sólido para sobrepor o conteúdo */
  padding: 1rem;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  z-index: 100;             /* mantém o header acima dos outros elementos */
}
```

**🟢 Resultado:**  
Quando o usuário rolar a página, o `<header>` acompanha até o topo e, a partir daí, **permanece visível**.

---

## 🚨 Cuidados importantes

1. O elemento **pai do sticky não pode ter `overflow: hidden` ou `overflow: auto`**, pois isso quebra o efeito.  
2. O sticky **só atua dentro da área do contêiner pai** (quando o pai termina, ele “solta”).  
3. É recomendável usar `z-index` e `background` para evitar sobreposição de conteúdo.  

---

## 💡 Quando usar

- Cabeçalhos de site (menus fixos no topo)  
- Tabelas longas (títulos de colunas fixos)  
- Seções de artigos (título da seção permanece visível)  
- Navegações internas (âncoras de conteúdo)

---
