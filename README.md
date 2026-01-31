# Mini Git – Implémentation en Rust

Ce projet est une implémentation simplifiée de certaines commandes internes de Git, réalisée en Rust dans le cadre d’un exercice pédagogique.

## Fonctionnalités implémentées

Les commandes suivantes sont supportées :

- `hash-object -w <file>`  
  Crée un blob à partir d’un fichier et l’écrit dans `.git/objects`.

- `ls-tree --name-only <tree_sha>`  
  Liste les entrées d’un tree Git (noms uniquement).

- `write-tree`  
  Crée récursivement un tree à partir du contenu du répertoire courant (en ignorant `.git`).

- `commit-tree <tree_sha> -p <parent_sha> -m <message>`  
  Crée un commit à partir d’un tree, avec un parent et un message.

## Organisation du projet

- Toute la logique est regroupée dans un seul fichier `main.rs`
- Les objets Git (blob, tree, commit) sont écrits dans `.git/objects` conformément au format Git
- Les entrées sont triées alphabétiquement, comme dans Git

## Hypothèses et simplifications

- Tous les fichiers du répertoire de travail sont considérés comme « staged »
- Un seul parent est accepté pour `commit-tree`
- Le nom, l’email et le timestamp du commit sont codés en dur
- Le message de commit est sur une seule ligne

## Compilation et exécution

```bash
cargo build
cargo run -- <commande>
# RUST-S1
