# Configurando Jenv Mac

- Instale Jenv. `$ brew install jenv`
- Execute os seguintes comandos abaixo

```fallback
  $ echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.bash_profile
  $ echo 'eval "$(jenv init -)"' >> ~/.bash_profile
```

- Antes de começa, execute o camando  `unset JAVA_TOOL_OPTIONS`em seu terminal. Sem isso, o comando a seguir abaixo não funcionará conforme o esperado.
- Verifique os diretórios de instalação do jdk .. e execute os comandos abaixo conforme apropriado para você ..

```fallback
$ jenv add /Library/Java/JavaVirtualMachines/jdk-10.0.1.jdk/Contents/Home
```

Você pode adicionar vários jdks se quiser.

- Digite `jenv versions`no terminal. Você veria algo semelhante a isto ..

```fallback
  system (set by /Users/sujithsreekumar/.jenv/version)
  - 1.8
  - 1.8.0.92
  - 10.0
  - 10.0.1
  - 9.0
  - 9.0.1
  - oracle64-1.8.0.92
  - oracle64-10.0.1
  - oracle64-9.0.1
```

Você pode remover aqueles como `oracle64-1.8.0.92`, `oracle64-10.0.1`etc. que foram adicionados por si só, usando o comando `jenv remove oracle64-1.8.0.92`. Mas isso é totalmente opcional ... Você pode deixá-los lá se quiser. Sem problemas.

Existem mais algumas coisas que você precisa fazer para que ele funcione corretamente ...

- Execute os seguintes comandos se estiver usando o maven:

```fallback
  $ jenv enable-plugin maven
  $ jenv enable-plugin export
```

* Caso  você receber erros informando que o comando enable-plugin não foi encontrado, você deve reiniciar seu terminal e as coisas devem funcionar corretamente depois disso.

Eu tive que correr `jenv enable-plugin export`porque meu `jenv`não era capaz de controlar o meu `JAVA_HOME`. Além disso, a falha na execução `jenv enable-plugin maven`gerará erros estranhos ao tentar compilar seu projeto.

Agora .. Você está pronto ...



https://developer.bring.com/blog/configuring-jenv-the-right-way/