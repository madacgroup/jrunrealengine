# Controle de Projetos · Unreal Engine

App de página única (HTML + JavaScript, sem build e sem dependências) para controlar o dia a dia da equipe de Unreal Engine:

- **Painel do dia:** bases matriz (A, B, C), tema em Preview e tema Final (gravação), e o que cada profissional está fazendo.
- **Histórico de projetos:** projetos criados e executados, com status, datas, anotações e prints.
- **Instruções:** por projeto e por módulo, com objetos, tipo de entrada de vídeo, exports de animação e anotações.
- **Backup:** exporta e importa todos os dados em JSON.

## Publicar no GitHub Pages

1. No GitHub, crie um repositório novo (ex.: `controle-projetos-ue`).
2. Envie o arquivo `index.html` para a raiz do repositório (**Add file → Upload files**) e faça o commit na branch `main`.
3. Vá em **Settings → Pages**. Em **Build and deployment**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`, e salve.
4. Em um ou dois minutos o app fica em `https://SEU-USUARIO.github.io/controle-projetos-ue/`.

Pelo terminal, o equivalente é:

```bash
git init
git add index.html README.md
git commit -m "Controle de projetos UE"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/controle-projetos-ue.git
git push -u origin main
```

Depois ative o Pages como no passo 3.

## Como os dados são guardados

Os dados ficam no `localStorage` do navegador, separados por endereço. Isso significa que:

- Cada pessoa e cada navegador vê apenas o que preencheu ali; nada é enviado ao GitHub.
- A versão hospedada começa vazia. Para levar os dados da versão antiga, use a aba **Backup**: exporte na antiga e importe na nova.
- Faça backup de vez em quando. Limpar os dados do navegador apaga tudo.
- Os prints são reduzidos antes de salvar, mas o navegador tem limite de espaço (cerca de 5 MB). O app avisa quando enche.

## Próximo passo: equipe compartilhada

Para os três profissionais verem o mesmo painel, é preciso um armazenamento compartilhado (por exemplo Firebase ou Supabase). O GitHub Pages só serve arquivos estáticos e não guarda dados da equipe.

## Observação sobre privacidade

Em conta gratuita, o GitHub Pages de um repositório público é público: qualquer pessoa com o link abre o app. Como os dados não ficam no repositório, nada do trabalho fica exposto, apenas o aplicativo vazio.
