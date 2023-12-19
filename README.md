# Лабораторная работа 2, Харитончик Егор 3 курс 12 групп

## База данных состоит из двух справочников: Компьютерные компоненты и Производители.

### Справочник Компьютерные компоненты:
* Id компонента (primary key)
* Название компонента
* Тип компонента
* Цена
* Год выпуска
* Id производителя (foreign key)

### Справочник Производители:
* Id производителя (primary key)
* Название производителя
* Страна производства
* Год основания

## Описание базы данных:
База данных будет сделана в MySQL и там же с ней выполняться работы.

### Скрипты для создания таблиц бд:
```
CREATE TABLE Components (
    component_id INT PRIMARY KEY AUTO_INCREMENT,
    component_name VARCHAR(255) NOT NULL,
    component_type VARCHAR(255),
    price DECIMAL(10,2),
    release_year DATE,
    manufacturer_id INT,
    FOREIGN KEY (manufacturer_id) REFERENCES Manufacturers(manufacturer_id)
);
```

```
CREATE TABLE Manufacturers (
    manufacturer_id INT PRIMARY KEY AUTO_INCREMENT,
    manufacturer_name VARCHAR(255) NOT NULL,
    country VARCHAR(255),
    foundation_year INT
);
```

## Схема базы данных
![ ](https://github.com/lJegerl/lab2_database/blob/main/%D0%A2%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D1%8B.png)

## Примеры заполнения

```
INSERT INTO Manufacturers (manufacturer_name, country, foundation_year) VALUES
('Intel', 'США', 1968),
('NVIDIA', 'США', 1993),
('Samsung', 'Южная Корея', 1938);
```

```
INSERT INTO Components (component_name, component_type, price, release_year, manufacturer_id) VALUES
('Intel Core i7', 'Процессор', 300.50, '2020-01-01', 1),
('NVIDIA GeForce RTX 3080', 'Видеокарта', 699.99, '2020-09-01', 2),
('Samsung 970 EVO', 'Жесткий диск', 149.99, '2018-03-01', 3);
```
