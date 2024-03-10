O comando `git stash` é usado para temporariamente armazenar (ou "esconder") as alterações não commitadas no diretório de trabalho e no índice, permitindo que você limpe o seu diretório de trabalho sem cometer as alterações incompletas. Isso é útil quando você deseja alternar rapidamente para outra tarefa ou ramo, mas não deseja comprometer suas alterações parciais.

Aqui estão algumas operações comuns que você pode realizar com o `git stash`:

1. **Armazenar Alterações**: Você pode armazenar as alterações não commitadas no stash usando o comando `git stash`. Isso criará uma entrada no stash contendo as alterações e as removerá do seu diretório de trabalho.
```bash
$ git stash
```

- **Aplicar Alterações Armazenadas**: Para aplicar as alterações armazenadas do stash de volta ao seu diretório de trabalho, você pode usar o comando `git stash apply`. Isso aplica as alterações mais recentes do stash, mas não as remove do stash.

```bash
$ git stash apply
```

- **Listar Stashes**: Para listar todas as entradas no stash, você pode usar o comando `git stash list`. Isso exibirá um histórico de todas as alterações armazenadas no stash.

```bash
$ git stash list
stash@{0}: WIP on branch_name: commit_message
stash@{1}: On branch_name: commit_message
```

- **Aplicar e Remover Alterações**: Se você deseja aplicar as alterações armazenadas e removê-las do stash em uma única operação, pode usar o comando `git stash pop`.

```bash
$ git stash pop
```

- **Limpar Stash**: Para limpar todas as entradas no stash, você pode usar o comando `git stash clear`.

```bash
$ git stash clear
```

O `git stash` é uma ferramenta útil para gerenciar alterações temporárias no seu diretório de trabalho, permitindo que você as armazene e reaplique conforme necessário sem comprometer seu histórico de commits. Isso é especialmente útil ao alternar entre tarefas ou quando você precisa reorganizar seu trabalho sem perder alterações importantes.