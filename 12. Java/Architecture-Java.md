# Architecture de Java

## Qu’est-ce que Java ?

Java est un langage de programmation orienté objet et multiplateforme.

Il suit le principe : "Write Once, Run Anywhere"  
(Un programme écrit en Java peut s’exécuter sur différents systèmes sans être réécrit.)

---

## Comment fonctionne Java ?

1. Le développeur écrit un fichier `.java`
2. Le compilateur le transforme en bytecode (`.class`)
3. La JVM exécute ce bytecode sur le système d’exploitation

### Schéma simplifié

```build
Développeur
   ↓
Code (.java)
   ↓
Compilation (JDK)
   ↓
Bytecode
   ↓
  JVM
   ↓
Système d’exploitation
```

---

## JVM, JDK & JRE

### JVM (Java Virtual Machine)

La JVM est un programme qui :

- Exécute le [bytecode](#bytecode)
- Permet à Java d’être multiplateforme
- Gère la mémoire ([Garbage Collector](#garbage-collector))

Sans JVM, un programme Java ne peut pas fonctionner.

---

### JDK (Java Development Kit)

Le JDK est l’outil nécessaire pour développer en Java.

Il contient :

- Le compilateur (`javac`)
- La JVM
- Les bibliothèques Java

JDK = tout ce qu’il faut pour coder et exécuter Java.

---

### JRE (Java Runtime Environment)

Le JRE permet uniquement d’exécuter un programme Java.
Il contient la JVM et les bibliothèques nécessaires.

---

#### Compiler en ligne de commande

```bash
javac -d build src/MonProgramme.java
```

- `javac` : lance le compilateur Java  
- `-d build` : indique le dossier de destination des fichiers `.class`  
- `src/MonProgramme.java` : fichier source à compiler  

Les fichiers compilés seront générés dans le dossier `build`.

#### Exécuter le programme

```bash
java -cp build MonProgramme
```

- `java` : lance la JVM  
- `-cp build` : indique le [classpath](#classpath) (où se trouvent les fichiers `.class`)  
- `MonProgramme` : nom de la classe contenant la méthode `main`  

---

## Gestion de la mémoire

Java utilise un [Garbage Collector](#garbage-collector).
Il libère automatiquement la mémoire des objets non utilisés.
Le développeur n’a pas besoin de gérer la mémoire manuellement.

---

## Les différentes éditions de Java

Java existe en plusieurs éditions selon l’usage.

### Java SE (Standard Edition)

Version standard de base.

Permet de créer :

- Applications desktop
- Applications console
- Programmes classiques

C’est le socle principal de Java.

---

### Jakarta EE (anciennement Java EE)

Extension de Java SE pour les applications d’entreprise.

Utilisé pour :

- Applications web
- API REST
- Applications distribuées
- Systèmes métier complexes

---

### Java Embedded

Version adaptée aux systèmes embarqués.

Utilisé pour :

- Objets connectés (IoT)
- Matériel industriel
- Équipements électroniques

---

## Versions de Java

Java évolue avec des versions régulières (Java 8, 11, 17, 21, 23 ...).

Certaines versions sont dites LTS (Long Term Support).
Elles sont maintenues plus longtemps et utilisées en entreprise.

---

## Définitions

### Bytecode

Le bytecode est un code intermédiaire généré par le compilateur Java.
Il n’est pas spécifique à un système d’exploitation.
Il est exécuté par la JVM.

### Classpath

Le classpath est le chemin où la JVM cherche les classes compilées (.class).
Il peut contenir des dossiers ou des fichiers .jar.

### Garbage Collector

Le Garbage Collector est un mécanisme automatique de gestion de la mémoire.

Il libère automatiquement la mémoire occupée par les objets qui ne sont plus utilisés.

Cela évite au développeur de devoir gérer la mémoire manuellement (contrairement à des langages comme C ou C++).
