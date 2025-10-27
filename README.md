<div style="text-align:center">
  <h1 align="center"> 1TDSPB - Front-end </h1>
  <p align="center">
    <img width="300" height="300" alt="Pascal o mascote" src="https://github.com/user-attachments/assets/75b21522-10b6-47cc-8d19-b8fa4aa49b3b" />
  </p>
</div>

Opa!  esse é o nosso repositório das aulas de front-end, fique a vontade para estudar!

### Branches

Nossa convensão é a seguinte, a sua branch tem o seu rm como por exemplo:

```
rm555666
```

## Exercícios

Agora temos uma pasta só para os exercícios, assim não nos perdemos mais! 

- [Exercício 1 - entrega no dia 14/10](exercicios/1.md)
- [Exercício 2 - entrega no dia ](exercicios/2.md)
- [Exercício 3 - entrega no dia ](exercicios/3.md)
- [Exercício 4 - entrega no dia ](exercicios/4.md)
- [Exercício 5 - entrega no dia ](exercicios/5.md)
- [Exercício 6 - entrega no dia ](exercicios/6.md)
- [Exercício 7 - entrega no dia ](exercicios/7.md)
- [Exercício 8 - entrega no dia ](exercicios/8.md)
- [Exercício 9 - entrega no dia ](exercicios/9.md)
- [Exercício 10 - entrega no dia ](exercicios/10.md)

## FAQ

Q: Como mudo a minha branch?

R: `git checkout -b [seu rm]`

Q: Minha branch não tá igual a do professor

R: É so dar merge: `git merge main`

Q: Tem um monte de cor diferente aqui

R: Isso é um conflito, você precisa resolver abrindo o VSCode e resolvendo o conflito.


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
