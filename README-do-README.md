# README do README

Se você abriu o código deste repositório, talvez tenha notado que ele foge um pouco da estrutura tradicional (e espero que tenha gostado!). Eu queria que meu perfil funcionasse como uma "pseudo landing page": limpa, responsiva e com vida.

Se você achou a estrutura interessante e quer replicar algumas ideias no seu próprio perfil, aqui está o detalhamento de como tudo foi feito (e as gambiarras necessárias para driblar as limitações de segurança do GitHub).

---

## O Banner

O maior desafio em personalizar o perfil como eu queria foi passar pelas barreiras de segurança da plataforma. O renderizador de Markdown do GitHub bloqueia qualquer tag `<script>` ou animação em CSS direto no código. A solução foi usar um arquivo SVG (`banner.svg`), já que eles suportam estilização via `<style>`. Desse modo, toda a animação de digitação foi programada em CSS puro dentro dele:

* **Emulação da digitação:** Todo o texto (*Hello! I'm AugustoCGM*) foi animado utilizando a função `steps()` do CSS. O código calcula a largura exata de cada caractere para emular o "pulo" mecânico entre as letras de uma digitação real. 
* **O fundo com os mockups:** Criei a arte em um programa de edição (usei o Affinity), fiz o upload no Base64 (https://www.base64-image.de) e inseri o link do repositório da imagem
* **Personalização fácil:** Caso queira algo mais simples, basta apagar a tag `<image>` (por volta da linha 116). Há um fundo sólido por trás para o caso de o SVG demorar a carregar (você pode alterar a cor dele mudando o código hexadecimal do `fill` na linha 113).

---

## Efeito Sanfona nas Seções

Para evitar um paredão de texto e poupar scroll — e fadiga da minha parte por ter que scrollar várias vezes até o fim do README sempre que precisar ver algo no meu perfil —, optei por usar as tags HTML `<details>` e `<summary>`. Elas funcionam perfeitamente dentro do Markdown e criam aquele efeito de recolhimento (sanfona) nas seções de "Sobre mim" e "Meus projetos".

---

## Badges e Ícones

Eu curto a ideia de usar aqueles *badges* tradicionais que você já deve ter visto em vários perfis; eles ajudam a indicar visualmente as tecnologias com as quais você trabalha. No entanto, sinto que o excesso deles gera o efeito contrário, deixando o visual poluído. Para resolver isso:

* **Skill Icons:** Usei a API do [Skill Icons](https://skillicons.dev/) para puxar de forma limpa as logos das linguagens e frameworks que utilizo.
* **Assets locais:** Para ferramentas específicas que não estavam lá (como o Affinity e o Pacote Office), baixei os PNGs oficiais e os organizei em uma pasta de `assets` dentro do repositório.

---

O código inteiro é totalmente aberto. Fique à vontade para fuçar o repositório, copiar o que achar útil e adaptar para criar a sua própria vitrine. Espero que este perfil sirva de inspiração para a construção do seu!
