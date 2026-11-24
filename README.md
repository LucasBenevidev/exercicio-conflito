# Exercício: resolva o conflito

Exercício da pílula **Controle de Versão** (pós-graduação do CEUB).

A branch `main` e a branch `exercicio-conflito` mudaram **a mesma linha** do arquivo `receita.md`:

- na `main`, a receita leva **2 ovos e 1 gema**;
- na `exercicio-conflito`, a receita leva **4 ovos**.

Sua missão é integrar as duas branches e decidir a versão final.

## Opção A: só pelo navegador (não precisa instalar nada)

1. Clique em **Fork**, no alto desta página. **Desmarque** a opção *Copy the `main` branch only* e confirme.
2. No **seu** fork, abra a aba **Pull requests** e clique em **New pull request**.
   - Confira que *base repository* é o seu fork, não o original.
   - Escolha **base: `main`** e **compare: `exercicio-conflito`**.
3. Clique em **Create pull request**. O GitHub vai avisar que há conflito. Clique em **Resolve conflicts**.
4. No editor, escolha a quantidade de ovos e **apague** as linhas `<<<<<<<`, `=======` e `>>>>>>>`.
5. Clique em **Mark as resolved**, depois em **Commit merge** e, por fim, em **Merge pull request**.

## Opção B: pelo terminal (Git instalado)

```bash
git clone https://github.com/SEU-USUARIO-DO-GITHUB/exercicio-conflito.git   # o seu fork
cd exercicio-conflito
git merge origin/exercicio-conflito      # o conflito aparece aqui
# edite receita.md: escolha a quantidade de ovos e apague os marcadores
git add receita.md
git commit --no-edit
git log --oneline --graph --all
git push
```

## Como saber se deu certo?

Rode `git log --oneline --graph` (ou veja a aba **Commits** do seu fork). Deve aparecer um commit de merge unindo as duas linhas do histórico, e o `receita.md` não deve ter nenhum marcador de conflito.
