# Esoft

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Home Visualization</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  
  <!-- Main Container -->
  <div class="home-container">
    
    <!-- House Base -->
    <div class="house-base"></div>

    <!-- Roof -->
    <div class="roof"></div>
  
    <!-- Window -->
    <div class="window"></div>
  
    <!-- Chimney -->
    <div class="chimney"></div>

  </div>
  
</body>
</html>

* {
  box-sizing: border-box;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f5f5dc; /* Light Goldenrod Yellow */
}

.home-container {
  position: relative;
  width: 400px;
  height: 267px; /* The ratio of the house is approximately 1.7391 */
}

/* House Base */
.house-base {
  position: absolute;
  bottom: 0;
  left: calc(50% - 100px);
  width: 200px;
  height: 150px;
  background-color: brown; /* Brown */
}

/* Roof */
.roof {
  position: absolute;
  top: 0;
  left: calc(50% - 125px);
  width: 0;
  height: 0;
  border-left: 125px solid transparent;
  border-right: 125px solid transparent;
  border-bottom: 125px solid orange; /* Orange */
}

/* Window */
.window {
  position: absolute;
  top: 60%;
  left: calc(50% - 25px);
  width: 50px;
  height: 50px;
  background-color: blue; /* Blue */
  border-radius: 50%;
}

/* Chimney */
.chimney {
  position: absolute;
  top: 50px;
  right: 100px;
  width: 20px;
  height: 50px;
  background-color: black; /* Black */
}



function deepClone(obj, hash = new WeakMap()) {
    if (hash.has(obj)) return hash.get(obj);

    // Handling primitive types and functions
    let result;
    switch (typeof obj) {
        case 'object':
            if (obj === null) {
                return null;
            } else if ('constructor' in obj && obj instanceof RegExp) {
                result = new obj.constructor(obj);
            } else if ('constructor' in obj && obj instanceof Date) {
                result = new obj.constructor(obj.getTime());
            } else if ('[Symbol.iterator]' in obj || Array.isArray(obj)) {
                result = Array.from(obj, v => deepClone(v, hash));
            } else {
                result = {};
            }

            break;

        default:
            return obj;
    }

    hash.set(obj, result);

    for (let key of Object.keys(obj)) {
        const val = obj[key];
        result[key] = deepClone(val, hash);
    }

    // Copying symbols
    Reflect.ownKeys(obj).forEach((key) => {
        if (typeof key!== "symbol") return;
        result[key] = Reflect.getOwnPropertyDescriptor(obj, key);
    });

    return result;
}

const originalObj = {...};
const clonedObj = deepClone(originalObj);

def is_valid_sequence(s):
    stack = []

    # Словарь, хранящий парные скобки
    brackets_map = {'(': ')', '[': ']', '{': '}'} 

    for char in s:

        # Если символ является открывающей скобкой, добавляем его в стэк
        if char in brackets_map: 
            stack.append(char)

        # Символ является закрывающей скобкой
        elif len(stack)==0 or brackets_map[stack[-1]]!= char:

            # Если в стэке нет соответствующей открывающей скобки или они расставлены неправильно
            return False 

        else: 
            stack.pop()

    # Все скобочные последовательности были закрыты правильно
    return len(stack) == 0 


# Тестовые случайные данные 
print(is_valid_sequence("()"))        # Выводит: True
print(is_valid_sequence("()[{}]"))    # Выводит: True
print(is_valid_sequence("(]"))         # Выводит: False
print(is_valid_sequence("([)] "))     # Выводит: False
print(is_valid_sequence("{[]}"))      # Выводит: True

Для решения этих задач использовал нейронку, так как сам еще не умею программировать.
Хотел бы научиться у вас!
