# Cours-de-C-Introduction-et-Concepts-de-Base

## **1️⃣ Structure de base d’un programme C++**
```cpp
#include <iostream>  // Inclut la bibliothèque pour l'affichage et l'entrée/sortie
using namespace std; // Utilise l'espace de noms std pour éviter d'écrire std:: devant cout

int main() { // Point d'entrée principal du programme
    cout << "Bonjour, C++ !" << endl; // Affiche un message à l'écran suivi d'un retour à la ligne
    return 0;  // Indique que le programme s'est terminé correctement
}
```

---

## **2️⃣ Variables et Types de Données**
```cpp
#include <iostream>  // Inclusion de la bibliothèque standard d'entrée/sortie
using namespace std; // Évite d'avoir à écrire std:: devant cout et cin

int main() {
    int age = 25;  // Déclaration et initialisation d'une variable entière
    double pi = 3.14159;  // Déclaration d'un nombre à virgule flottante en double précision
    char lettre = 'A';  // Stocke un seul caractère
    bool estValide = true;  // Valeur booléenne (true ou false)
    string nom = "Sabine";  // Chaîne de caractères (nécessite <string>)

    // Affiche le nom et l'âge sur la console
    cout << "Nom : " << nom << ", Age : " << age << endl;

    return 0; // Retourne 0 pour indiquer un programme terminé avec succès
}
```

---

## **3️⃣ Conditions et Boucles**
### **Conditions (`if`, `else if`, `else`)**
```cpp
int nombre = 10;  // Déclaration d'un entier

if (nombre > 0) {  // Vérifie si le nombre est positif
    cout << "Nombre positif" << endl;
} else if (nombre < 0) {  // Vérifie si le nombre est négatif
    cout << "Nombre négatif" << endl;
} else {  // Si aucune des conditions précédentes n'est vraie, c'est que le nombre est 0
    cout << "Nombre nul" << endl;
}
```

---

### **Boucle `for`** (répète un bloc de code un nombre défini de fois)
```cpp
for (int i = 0; i < 5; i++) { // i commence à 0 et s'incrémente jusqu'à 4 (5 itérations)
    cout << "Itération : " << i << endl; // Affiche la valeur de i à chaque itération
}
```

---

### **Boucle `while`** (répète tant que la condition est vraie)
```cpp
int compteur = 0;  // Initialisation de la variable compteur
while (compteur < 3) {  // Tant que compteur est inférieur à 3, la boucle s'exécute
    cout << "Compteur : " << compteur << endl;
    compteur++;  // Incrémente la variable compteur
}
```

---

### **Boucle `do while`** (exécute au moins une fois avant de vérifier la condition)
```cpp
int x = 0;  // Initialisation de x
do {
    cout << "Valeur de x : " << x << endl;
    x++;  // Incrémente x
} while (x < 3);  // Vérifie si x est encore inférieur à 3
```

---

## **4️⃣ Fonctions**
```cpp
#include <iostream>
using namespace std;

// Définition d'une fonction qui prend deux nombres et retourne leur somme
int addition(int a, int b) {
    return a + b; // Additionne les deux nombres et renvoie le résultat
}

int main() {
    int resultat = addition(5, 10); // Appelle la fonction avec les valeurs 5 et 10
    cout << "Résultat : " << resultat << endl; // Affiche le résultat de l'addition
    return 0;
}
```

---

## **5️⃣ Tableaux et Vecteurs**
### **Tableau statique**
```cpp
int nombres[5] = {1, 2, 3, 4, 5};  // Tableau contenant 5 éléments
cout << "Premier élément : " << nombres[0] << endl; // Affiche le premier élément (indice 0)
```

### **Vecteur dynamique (`#include <vector>`)**
```cpp
#include <vector>  // Inclusion de la bibliothèque vector

vector<int> valeurs = {10, 20, 30};  // Création d'un vecteur avec trois éléments
valeurs.push_back(40);  // Ajoute 40 à la fin du vecteur
```

---

## **6️⃣ Programmation Orientée Objet (POO)**
```cpp
#include <iostream>
using namespace std;

// Définition d'une classe Personne
class Personne {
public:
    string nom;  // Attribut pour stocker le nom
    int age;  // Attribut pour stocker l'âge

    // Constructeur qui initialise les attributs avec des valeurs fournies
    Personne(string n, int a) {
        nom = n;
        age = a;
    }

    // Méthode qui affiche les informations de la personne
    void afficher() {
        cout << "Nom : " << nom << ", Age : " << age << endl;
    }
};

int main() {
    Personne p1("Sabine", 30);  // Création d'un objet de la classe Personne
    p1.afficher();  // Appelle la méthode afficher() pour afficher les informations
    return 0;
}
```

---

## **📌 Prochaines notions**
- **Gestion de la mémoire (`new / delete`)** ✅
- **Héritage et polymorphisme** ✅
- **Fichiers et flux (`fstream`)** ✅
- **Pointeurs et références** ✅

D'accord ! Je vais expliquer chaque partie du code en détail avec des commentaires ligne par ligne.  

---

## 📌 **1. Gestion de la mémoire (`new` / `delete`)**  
L'allocation dynamique permet de réserver de la mémoire à l'exécution.

### **🔹 Allocation et libération d’un entier**
```cpp
#include <iostream>
using namespace std;

int main() {
    int* ptr = new int;  // 🔹 Alloue un entier dans la mémoire dynamique
    *ptr = 42;           // 🔹 Affecte la valeur 42 à l'adresse pointée par ptr
    cout << "Valeur : " << *ptr << endl;  // 🔹 Affiche la valeur stockée

    delete ptr;  // 🔹 Libère la mémoire allouée dynamiquement
    return 0;
}
```
✅ `new int` crée un entier dans la mémoire dynamique.  
✅ `delete ptr` libère cette mémoire pour éviter les fuites.  

---

### **🔹 Allocation d’un tableau dynamique**
```cpp
int* tab = new int[5];  // 🔹 Alloue un tableau de 5 entiers dans la mémoire dynamique

for (int i = 0; i < 5; i++) {
    tab[i] = i * 10;  // 🔹 Remplit le tableau avec 0, 10, 20, 30, 40
    cout << tab[i] << " ";  // 🔹 Affiche les valeurs
}

delete[] tab;  // 🔹 Libère la mémoire du tableau
```
✅ `new int[5]` alloue un tableau de 5 entiers.  
✅ `delete[] tab` libère la mémoire (attention : utiliser `delete[]` pour les tableaux).  

---

## 📌 **2. Héritage et Polymorphisme**
L’héritage permet de créer une classe `Chien` qui hérite de `Animal`.  

### **🔹 Héritage simple**
```cpp
class Animal {
public:
    void manger() {
        cout << "L'animal mange." << endl;
    }
};

class Chien : public Animal {  // 🔹 Chien hérite de Animal
public:
    void aboyer() {
        cout << "Le chien aboie." << endl;
    }
};

int main() {
    Chien monChien;  
    monChien.manger();  // 🔹 Méthode héritée de Animal
    monChien.aboyer();  // 🔹 Méthode propre à Chien
    return 0;
}
```
✅ `Chien` hérite de `Animal`, donc `manger()` est accessible dans `Chien`.  

---

### **🔹 Polymorphisme avec méthodes virtuelles**
```cpp
class Animal {
public:
    virtual void faireSon() { cout << "Son d'animal" << endl; }  // 🔹 Méthode virtuelle
};

class Chien : public Animal {
public:
    void faireSon() override { cout << "Wouf Wouf!" << endl; }  // 🔹 Redéfinition
};

int main() {
    Animal* ptr = new Chien();  // 🔹 Un pointeur de base peut pointer sur un objet dérivé
    ptr->faireSon();  // 🔹 Affiche "Wouf Wouf!" au lieu de "Son d'animal" grâce au polymorphisme

    delete ptr;  // 🔹 Libération de la mémoire
}
```
✅ `virtual` permet d’appeler la méthode de la classe dérivée (`Chien`) même avec un pointeur vers la classe de base.  

---

## 📌 **3. Fichiers et flux (`fstream`)**
Manipuler des fichiers en lecture et écriture.

### **🔹 Écriture dans un fichier (`ofstream`)**
```cpp
#include <fstream>  // 🔹 Inclure la bibliothèque pour les fichiers
using namespace std;

int main() {
    ofstream fichier("exemple.txt");  // 🔹 Ouvre un fichier en écriture
    fichier << "Bonjour, ceci est un fichier texte en C++ !\n";  // 🔹 Écrit dans le fichier
    fichier.close();  // 🔹 Ferme le fichier pour enregistrer les changements
    return 0;
}
```
✅ `ofstream` permet d’ouvrir un fichier en mode écriture et d’y écrire du texte.  

---

### **🔹 Lecture d’un fichier (`ifstream`)**
```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream fichier("exemple.txt");  // 🔹 Ouvre le fichier en lecture
    string ligne;
    while (getline(fichier, ligne)) {  // 🔹 Lit le fichier ligne par ligne
        cout << ligne << endl;  // 🔹 Affiche chaque ligne à l’écran
    }
    fichier.close();  // 🔹 Ferme le fichier
    return 0;
}
```
✅ `ifstream` permet d’ouvrir un fichier en lecture et d’en extraire le contenu.  

---

## 📌 **4. Pointeurs et Références**
Les pointeurs stockent une adresse mémoire, les références sont des alias.

### **🔹 Pointeurs**
```cpp
int a = 10;
int* p = &a;  // 🔹 p stocke l’adresse de a
cout << "Valeur de a : " << *p << endl;  // 🔹 Affiche 10 (déréférencement)
```
✅ `*p` permet d’accéder à la valeur stockée à l’adresse contenue dans `p`.  

---

### **🔹 Références**
```cpp
int x = 42;
int& ref = x;  // 🔹 ref est une référence vers x
ref = 100;  // 🔹 Modifie x
cout << x << endl;  // 🔹 Affiche 100
```
✅ Une référence est un alias d’une variable existante et ne peut pas être `NULL`.  

---

## 🚀 **Résumé**
✔️ **Gestion de mémoire (`new`/`delete`)** : Permet l’allocation dynamique, mais attention aux fuites.  
✔️ **Héritage & Polymorphisme** : L’héritage facilite la réutilisation du code et `virtual` permet un comportement dynamique.  
✔️ **Fichiers (`fstream`)** : Permet la lecture et l’écriture dans des fichiers.  
✔️ **Pointeurs & Références** : Les pointeurs manipulent des adresses, les références sont des alias.  


