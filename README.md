# tree@0.0.1

### Задание
Написать программу для работы с бинарным деревом поиска:
- `+` - добавить ключ
- `?` - найти ключ
- `=` - вывести на экран дерево
- `q` - выйти

### Замечания
Для реализации бинарного дерева поиска используйте класс следующего вида:
```
class tree_t
{
private:
    struct node_t {
        node_t * left;
        node_t * right;
        int key;
    };
private:
    node_t * root_;
public:
    void insert(int key);
    bool find(int key) const;
    void print(std::ostream & stream) const;
};
```

### Входные данные
Во входных данных заданы строки, следующего формата:
```
+ <число>
? <число>
=
q
```

### Примеры
```
+ 2
----2

+ 1
----2
--------1

+ 3
--------3
----2
--------1
? 1
true

? 4
false

=
--------3
----2
--------1

q
```

# tree@0.0.2

### Задание
- Сделать класс шаблоном
- Добавить метод удаления ключа
- Добавить метод сравнения деревьев
- Добавить поддержку списка инициализации
- Реализуйте тесты ко всем открытым методам класса

### Замечания
Для реализации бинарного дерева поиска используйте класс следующего вида:
```
template <typename T>
class tree_t
{
private:
    struct node_t {
        node_t * left;
        node_t * right;
        T key;
    };
private:
    node_t * root_;
public:
    tree_t(std::initializer_list<T> keys);
    auto operator==(tree_t const & other) const;
    void insert(T key);
    bool remove(T key);
    bool find(T key) const;
    void print(std::ostream & stream) const;
};
```
