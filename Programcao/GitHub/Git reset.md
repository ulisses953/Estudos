#Git 
O comando `git reset` é uma ferramenta poderosa no Git para manipular o histórico do seu repositório. Ele é usado para alterar a posição da HEAD (ponteiro para a última confirmação) e, opcionalmente, o índice (área de preparação) e o diretório de trabalho (arquivos locais). Existem três formas principais de usar o `git reset`, dependendo dos argumentos fornecidos:
1. **Soft Reset**:
    - `git reset --soft <commit>`: Este comando move a HEAD para o commit especificado, mantendo os arquivos no índice e no diretório de trabalho exatamente como estavam no commit que você está voltando. Isso significa que você está desfazendo os commits posteriores, mas mantendo as alterações desses commits preparadas para serem refeitas.
2. **Mixed Reset**:
    - `git reset --mixed <commit>` (ou simplesmente `git reset <commit>`): Este é o comportamento padrão do `git reset`. Ele move a HEAD para o commit especificado e redefine o índice para corresponder a este commit. No entanto, as alterações nos arquivos não são perdidas; elas ainda estão presentes no seu diretório de trabalho, mas não estão preparadas para commit.
3. **Hard Reset**:
    - `git reset --hard <commit>`: Este é o reset mais drástico. Ele move a HEAD e redefine o índice para o commit especificado, além de descartar todas as alterações não commitadas no diretório de trabalho. Isso significa que qualquer alteração desde o commit especificado será perdida irrevogavelmente. Portanto, tenha cuidado ao usar este comando, pois ele pode resultar na perda permanente de trabalho não commitado.
    - 
Além disso, você pode especificar o tipo de reset usando a opção `--soft`, `--mixed`, ou `--hard`. Se você não especificar nada, o `git reset` irá assumir `--mixed` como padrão.

É importante notar que o `git reset` é uma operação que reescreve o histórico do repositório. Portanto, é recomendável ter cuidado ao usá-lo, especialmente em repositórios compartilhados, para evitar problemas de sincronização e perda de trabalho.