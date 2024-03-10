#Git 
O comando `git branch` é usado para listar, criar ou excluir branches no repositório Git. Aqui estão algumas das operações comuns que podem ser realizadas com o `git branch`:

1. **Listar Branches**: Sem argumentos, o comando `git branch` lista todas as branches presentes no repositório local. O branch atualmente checado é marcado com um asterisco (`*`). ```
```bash
$ git branch
  branch1
* master
  branch2
```
2. **Criar Branches**: Para criar um novo branch, você pode usar o comando `git branch <nome_branch>`. Isso criará um novo branch no commit atual.
```bash
$ git branch new_branch
```
3. **Excluir Branches**: Para excluir um branch, use o comando `git branch -d <nome_branch>`. Este comando irá excluir o branch especificado, mas apenas se suas alterações já tiverem sido mescladas com outros branches. Se você deseja forçar a exclusão, mesmo que haja commits não mesclados, use `-D` em vez de `-d`.
   ```bash
$ git branch -d branch_para_excluir
```
4. **Renomear Branches**: O Git não fornece um comando direto para renomear branches, mas você pode fazer isso movendo o branch e criando um novo com o nome desejado. Por exemplo:
   ```bash
$ git branch -m nome_antigo nome_novo
```
5. **Verificar as Branches Remotas**: Para ver as branches remotas e seus respectivos rastreamentos, você pode usar o comando `git branch -r`.
   ```bash
$ git branch -r
  origin/branch_remota1
  origin/branch_remota2
```
6. **Criar um Novo Branch e Mudar Para Ele**: Você também pode criar um novo branch e mudar para ele em uma única etapa, usando o comando `git checkout -b <nome_branch>`.
   ```bash
$ git checkout -b novo_branch
```

Essas são algumas das operações mais comuns que você pode executar com o comando `git branch`. Ele é uma ferramenta essencial para gerenciar o fluxo de trabalho e as diferentes linhas de desenvolvimento em um repositório Git.