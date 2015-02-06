layout: oishi
title: Criando um blog com GitHub Pages e Hexo em menos de 10 passos
date: 2015-02-06 10:44:46
tags: GitHub
---
Já pensou em criar um site/blog em menos 10 minutos? De forma fácil, grátis e com deployment continuous?

Em um bate-papo com um grande amigo e frontender [Michael Villander](http://villander.github.io) onde discutíamos algumas ferramentas e a grande importância sobre os profissionais da nossa área contribuírem com a comunidade (um ótimo assunto pra mais tarde) decidi criar um artigo ensinado você criar um blog de forma fácil e espero que, com isso, você possa contribuir/divulgar/aprender/testar algo legal.

Pois bem, o GitHub tem um serviço excepcional, o [GitHub Pages](https://pages.github.com/). Onde você pode hospedar páginas estáticas, com JavaScript, HTML, CSS e imagens. Com ele você pode criar o seu blog baseado nos templates existentes ou utilizar algum framework como [Hexo](http://hexo.io/) (pra você que é Jedi em JavaScript) ou [Jekyll](http://jekyllrb.com/) (pra você que se diverte com Ruby). Como usei o Hexo, vamos utilizá-lo neste post.

Blá, blá, blá…. Vamos ao que interessa, né?! 

1 - Crie um novo repositório no GitHub com o padrão ``usarname.github.io``, pois será o domínio que o GitHub Pages vai usar e você também poderá colocar um [domínio próprio](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/) e faça clone do repositório

2 - Instale o Hexo com o comando ``$ npm install hexo -g`` (vale lembrar que você vai precisar do Node.js e Git instalados)

3 - Inicialize o Hexo com o comando hexo ``$ init username.github.io``, acesso o repositório e faça o build com ``$ npm install``

4 - Configure o seu arquivo ``_config.yml`` com as informações do seu blog e em deploy, adicione o repositório criado anteriormente
``` 
# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: github
  repository: git@github.com:usarname/usarname.github.io.git
```

5 - Crie seu primeiro post com ``$ hexo new [layout] <title>``  onde ``[layout]`` você irá usar [landscape](https://github.com/hexojs/hexo-theme-landscape), que vem por padrão com o Hexo, e o título do post

6 - Para gerar os arquivos estáticos, execute ``$ hexo generate``

7 - O seu primeiro post foi gerado, agora execute ``$ hexo server`` para testar e acesse a url ``localhost:4000``

8 Se estiver tudo ok, faça o deploy com ``$ hexo deploy`` e acesse o site com a URL ``https://username.github.io`` e voilà!!! 
	
O primeiro deploy leva algum tempo, algo em trono de 30 minutos segundo o GitHub. E ainda assim, não se preocupe, pois os próximos serão praticamente instâneos a cada commit, e como prometido, nosso site está com o tão desejado deployment continuous e com menos de 10 passos. Fácil, não? 


### Notas 

* Nosso arquivo de configuração é um [YML](http://en.wikipedia.org/wiki/YML), que diferentemente do json, usa a indentação
* Certifique-se que seu e-mail e chave SSH estão válidos no GitHub