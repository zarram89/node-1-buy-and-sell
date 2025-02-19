# REST API «Куплю-продам»

## Заметки по курсу

### 1. CLI

#### Обновление и переключение веток

```bash
# в вашей локальной копии переключитесь в ветку master
git checkout master
# заберите изменения из репозитория Академии¹ (или academy)
git pull academy master
# отправьте изменения ветки master в ваш форк на Гитхабе (или origin)
git push origin master
# когда вы обновили master, создайте ветку для выполнения задания
git checkout -b module2-task1

# в academy должна быть ссылка на репозиторий Академии. Если её там нет, добавьте
git remote add academy git@github.com:htmlacademy-nodejs-api/241042-six-cities-9.git
```

#### Установка nvm в macOS и Linux (Node Version Manager)

```bash
# установка на macOS
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

# установка на Linux через wget
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

# или через apt-get на Ubuntu или Debian
apt-get install curl

# Для Windows ставим nvm-windows или nodist

### проверяем установку и версию
nvm --version
```

#### Работа с nvm

```bash
# узнать версию
node --version

# установить LTS-резил
nvm install --lts 

# установить нужную вепрсию
nvm install 17

# посмотреть список установленных версий node
nvm list

# переключиться на нужную версию node use 16
nvm use 16.14.2

# или
nvm use 16

# помощь nvm --help
nvm --help
```

####  Инструмент REPL (Read Eval Print Loop)

```bash
 # вводим в консоль node и запускается REPL 
 node

 # для выхода вводим .exit или прерываем процесс Ctrl+C
```

Выводим сообщение из консоли в REPL
```03-first-application.js
console.log(`Hello, world from Node ${process.version}`);
```

```bash
node ./03-first-application.js 
### получим версию node
Hello, world from Node v22.13.0
```

#### TypeScript

Модификаторы
- private используется для определения приватных (закрытых) полей и методов. То есть полей и методов, которые применяются только внутри класса. Снаружи к ним нельзя получить доступ. 
- public публичные свойства и методы доступны как внутри класса, так и снаружи. Свойства и методы, объявленные без модификатора подразумеваются публичными.
- protected защищённые поля и методы. Такие поля доступны внутри класса и они наследуются. Это означает, что внутри наследника можно напрямую обращаться к таким свойствам и методам.

#### Интерфейсы
Интерфейсы — это один из способов определить контракт. Для этого класс должен реализовать интерфейс или как ещё часто говорят — имплементировать интерфейс.

```js
interface Musician {
  // Музыкант предоставляет информацию о
  // количестве гитар в коллекции
  readonly guitarCount: number;

  // Музыкант умеет играть
  play(): void;

  // Музыкант умеет здороваться
  hello(): void;
}

class GuitarPlayer implements Musician {
  // Тело класса
    constructor(
    public readonly guitarCount: number,
  ) {}

  public play() {
    console.log('Гитарист играет на гитаре.');
  }

  public hello() {
    console.log('Привет, я гитарист');
  }
}
```
Один класс может реализовывать несколько интерфейсов.
```js
class GuitarPlayer implements Musician, Vocalist {}
```
Проектирование на основе интерфейсов позволяет добиться гибкости. Наследование — один из сложных принципов ООП. С ним легко свернуть не туда, выстроив сложную и неправильную цепочку наследования. Интерфейсы более атомарны.

При использовании интерфейсов в TypeScript стоит помнить о нескольких нюансах. Если в одной области видимости объявлен интерфейс и класс с одинаковыми именами, то подразумевается, что класс реализует интерфейс. Поскольку имя класса совпадает с именем интерфейса и они объявлены в одной области видимости, подразумевается, что класс реализует интерфейс. Стоит упомянуть, что пользоваться этой возможностью стоит в исключительных ситуациях. Явное всегда лучше неявного.

Подведём итоги:

- Интерфейсы — один из способов определить контракт. Контракт не содержит деталей, только общие сведения. Имплементация происходит в классе, который реализует интерфейс.
- Для объявления интерфейса используется ключевое слово interface.
- Имя интерфейса начинается с прописной буквы. Может быть как существительным, так и глаголом.
- Интерфейс первичен. Проектируйте классы на основании интерфейса, а не наоборот.
- Интерфейс атомарен. Лучше несколько небольших интерфейсов, чем один большой.
- Для реализации интерфейса используется ключевое слово implements. Его указываем после имени класса.
- Один класс может реализовывать несколько интерфейсов. В этом случае все интерфейсы перечисляются через запятую.

### Node

#### Альтернативы, исправлены детские болезни Node

Bun и Deno

#### Фрэймворки с архитектурой, которой нет в Node

Express и Fastify (микрофрэймворки)
Nest.js и Adonis.js

#### Виды приложений на Node

- CLI
- HTTP Services (REST API)
- Desktop Apps
- Microservices

### NPM

#### Алиасы для команд

- -D — алиас для --save-dev;
- -E — алиас для --save-exact;
- i — алиас для install;
- un — алиас для uninstall;

### Command Line Interface (CLI)

#### 
