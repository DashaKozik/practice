# Kozik Daria
# Contact information
- #### Phone: +375295470391
- #### E-mail: dashaadada1981@gmail.com
- #### GitHub: DashaKozik
- #### Telegram: dashaa_dada
# About Me
#### I am 18 years old, finished the first year of the university (Specialty: Information systems and technologies in business management). I have good interpersonal skills, I work well in a team and I really want to learn and develop new skills. Also my strengths are in solving problems and  fast learning.  I want to gain knowledge and skills that will be enough for employment in the company.
# Skills
- #### HTML
- #### C++
- #### Java
- #### Git/GitHub
- #### node.js
# Code example
```c++
#include <iostream>
#include <string>
#include <fstream>
#include <list>
#include <algorithm>

using namespace std;

struct Node {
    int key;
    int value;
    Node* left;
    Node* right;
};

class Tree {
public:
    Tree() {
        root = nullptr;
    }

    void insert(int key, int value) {
        root = insertHelper(root, key, value);
    }

    Node* search(int key) {
        return searchHelper(root, key);
    }
    //открываем файл

    void loadFromFile(string filename) {    //открывает заданный файл и последовательно считывает 
        ifstream file(filename);             //пары ключ-значение из него, добавляя их в дерево 
        if (!file.is_open()) {
            cout << "Error opening file: " << filename << endl;
            return;
        }

        int key, value;
        while (file >> key >> value) {
            insert(key, value);
        }
        file.close(); // Закрытие файла.
    }

    void swapMinMax() {
        if (root == nullptr) {
            return;
        }

        Node* minNode = root;
        Node* maxNode = root;

        // ищем максимальный и минимальный элементы
        while (minNode->left != nullptr) {
            minNode = minNode->left;
        }
        while (maxNode->right != nullptr) {
            maxNode = maxNode->right;
        }

        // меняем
        int temp = minNode->value;
        minNode->value = maxNode->value;
        maxNode->value = temp;
    }

private:
    Node* root;
//рекурсивное добавление нового элемента в дерево
    Node* insertHelper(Node* node, int key, int value) {
        if (node == nullptr) {             //Если текущий узел равен nullptr, то создаётся 
                                          //новый узел с заданным ключом и значением,
                                           // а если ключ меньше текущего узла, то новый узел добавляется в левое поддерево,
                                           // а если больше, то в правое поддерево
            node = new Node;
            node->key = key;
            node->value = value;
            node->left = nullptr;
            node->right = nullptr;
        }
        else if (key < node->key) {
            node->left = insertHelper(node->left, key, value);
        }
        else if (key > node->key) {
            node->right = insertHelper(node->right, key, value);
        }
        else {
            node->value = value;
        }
        return node;
    }
//сравниваем

    Node* searchHelper(Node* node, int key) {                      //работает рекурсивно и ищет узел с заданным ключом в дереве
        if (node == nullptr || node->key == key) {            
            return node;
        }                                                      //текущий узел равен nullptr или ключ текущего узла равен заданному ключу,
        else if (key < node->key) {                            // то он возвращает текущий узел. Если заданный ключ меньше ключа текущего узла,
            return searchHelper(node->left, key);              // то поиск продолжается в левом поддереве, иначе - в правом
        }
        else {
            return searchHelper(node->right, key);
        }
    }
};

int main() {
    Tree tree;
    tree.loadFromFile("derev.txt");

    Node* minNode = tree.search(5);
    Node* maxNode = tree.search(12);

    cout << "Before swap: " << endl;
    cout << "Min: " << minNode->value << endl;
    cout << "Max: " << maxNode->value << endl;

    tree.swapMinMax();

    cout << "After swap: " << endl;
    cout << "Min: " << minNode->value << endl;
    cout << "Max: " << maxNode->value << endl;

    return 0;
}
```
# Experience
#### Educational projects (C++, node.js, HTML, java, Git/GitHub)
# Education
#### Vitebsk State Technological University, pecialty "Information systems and technologies in business management"
# Languages
- #### Russian
- #### Belarusian
- #### English
