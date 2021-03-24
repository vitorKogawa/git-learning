# Curso de Git (DIO)

Definição: git é uma tecnologia desenvolvida por Linus Torvalds (um dos principais desenvolvedores do kernel Linux), afim de conseguir versionar o código de um determinado projeto que está sendo desenvolvido por diversos programadores.

![https://www.extremetech.com/wp-content/uploads/2013/01/linuxwallpaper.jpg](https://www.extremetech.com/wp-content/uploads/2013/01/linuxwallpaper.jpg)

### Para utilizar o Git temos duas opções:

- Git bash: onde você utilizada a tecnologia através das linhas de comando
- Clientes para o git: Existem diversos clientes para o git , e eles oferecem interfaces gráficas bem amigáveis e intuitivas, facilitando bastante a usabilidade e disseminação do git pelo mundo do desenvolvimento, algumas delas são:

![https://d33v4339jhl8k0.cloudfront.net/docs/assets/586a9a59c697915403a08c1d/images/5a38d60504286346b0bc9fa7/file-guT1bRpSfE.png](https://d33v4339jhl8k0.cloudfront.net/docs/assets/586a9a59c697915403a08c1d/images/5a38d60504286346b0bc9fa7/file-guT1bRpSfE.png)

Github, GitLab, GitBucket respectivamente.

### Alguns comando básicos muito utilizados no terminal

- `ls` (list): lista todo o conteúdo do diretório em que você se encontra no momento.

![Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled.png](Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled.png)

- `cd` (change directory): você utiliza esse comando junto a um argumento , este argumento é o nome do diretório que você pretende acessar.

![Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%201.png](Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%201.png)

- `pwd`: (print work directory): mostra no terminal o diretório em que você está atualmente.

![Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%202.png](Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%202.png)

- `mkdir` (make directory): assim como o `cd` , você utiliza este comando juntamente com um argumento que é o nome do diretório que você pretende criar.

![Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%203.png](Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%203.png)

- `clear`: limpa todo o conteúdo do terminal , deixando a tela limpinha para você pode digitar muitos mais comandos.

**Como o Git funciona por debaixo dos panos**

- `**SHA1**`(Secure Hash Algorithm): é um algoritmo de encriptação, ele vai pegar o seu arquivo e vai "embaralhar" ele de uma maneira bem específica, e foi desenvolvido pela NSA (Agência de Segurança Nacional dos EUA).

    E é desta maneira que o Git identifica as modificações do arquivo. (através do SHA1)

    - Quando aplicado em algum arquivo o SHA1 vai gerar um conjunto de 40 caracteres único no mundo, assim se tornando uma forma curta de representar um arquivo, como na imagem abaixo.

    ![Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%204.png](Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%204.png)

- **`Objetos fundamentais`**
    - **Blobs**: armazena o sha1 gerado com base na modificação ou criação do arquivo.
    - **Trees**: apontam para blobs ou outras trees e são responsáveis por armazenar o nome do arquivo alterado / criado e gerar um sha1 para está modificação.
    - **Commit**: aponta para uma ou mais trees, armazenando metadados como: autor, data e hora de criação, além do sha1 gerado com base na molificação.

    ![https://shafiul.github.io/gitbook/assets/images/figure/objects-example.png](https://shafiul.github.io/gitbook/assets/images/figure/objects-example.png)

- **`Sistema distribuído e Segurança:`** por conta dos objetos fundamentais do git (blob, trees e commit) podemos perceber que está é uma tecnologia altamente segura, pois é praticamente impossível modificar um commit , pois para cada alteração de um arquivo é gerado um sha diferente referenciado o estado daquele arquivo num dado momento.

### Ciclo de vida no Git

No git os arquivos podem ser localizados em diferentes estágios, em geral temos duas zonas dentro do git elas são:

- **`Untracked`**: Zona dos arquivos desconhecidos com relação ao Git
- **`Tracked`**: Arquivos que o Git tem noção da existência.

E dentro da zona **`Tracked`** temos 3 subzonas que são as seguintes:

- **`Unmodified`**: sub-zona dos arquivos que não foram modificados
- **`Modified`**: sub-zona dos arquivos que foram modificados
- **`Staged`**: sub-zona dos arquivos que foram envelopados e estão prontas para serem enviados para o repositório remoto do seu projeto

![https://i.stack.imgur.com/QaeAZ.png](https://i.stack.imgur.com/QaeAZ.png)

⚠️ Quando os arquivos são movidos para a zona staged (geralmente pelo comando : **git add <arquivo.ext>**) eles automaticamente retornam para a sub-zona unmodified, e toda essa comparação para o git saber se um determinado arquivo foi modificado ou não é feito através da comparação do sha1 dos arquivos.

### Alguns comando básicos para lidar com as configurações do seu Git.

Para verificar todas as configurações do seu git basta digitar o seguinte comando:

```bash
git config --list
```

Tendo uma saída como

![Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%205.png](Curso%20de%20Git%20(DIO)%200d7a1bf04ad04692a56d33a02a8064ed/Untitled%205.png)

Abaixo segue os comando para você conseguir configurar o seu nome de usuário (nickname), nome e seu email, respectivamente:

```bash
git config --gobal user.nickname "Seu nickname/nome de usuário vem aqui"
git config --global user.name "Aqui vem seu nome"
git config --global user.email "Aqui vem seu email"
```

### Links

- No site oficial do [Git](https://git-scm.com) você pode explorar um pouco mais sobre essa incrível tecnologia através da sua documentação.
- Conheça um pouco mais sobre o [GitHub](https://github.com), [GitLab](https://about.gitlab.com) e [GitBucket](https://bitbucket.org) , que são uns dos principais clientes para você poder criar os seus repositórios remotos.

## Comando úteis

`git reset` remove do stage todos os últimos arquivos adicionados. (comando muito utilizado após um git add . / file)

`git reset --soft HEAD^` desfaz o último commit