---
# https://github.com/slidevjs/slidev/blob/v0.42.5/packages/types/src/config.ts
theme: eloc
color: 'red'
---

## `Types alias vs. Interfaces`

in Typescript

---

# What is Typescript?

---

#### "TypeScript adds additional syntax to JavaScript to support a tighter integration with your editor. Catch errors early in your editor"

---

#### Installation

```shell
npm i -g typescript
```

---

#### Create new project

```shell
tsc --init
```

---

#### Project structure

```shell
├── tsconfig.json
└── src
    └── index.ts
```

---

### Primitive Data Types

```typescript
let num: number;
let str: string;
let bool: boolean;

num = 123;
num = 123.456;
num = '123'; // Error

str = '123';
str = 123; // Error

bool = true;
bool = false;
bool = 'false'; // Error
```

---

### Any

```typescript
let power: any;

// Takes any and all types
power = '123';
power = 123;

// Is compatible with all types
let num: number;
power = num;
num = power;
```

---

### Unknown

```typescript
async function fetchData(): Promise<unknown> {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  return data;
}

const result = await fetchData();

if (typeof result === 'object' && result !== null) {
  // Now TypeScript recognizes 'result' as an object
}
```

---

### Never

```typescript
type Shape = 'circle' | 'square';

function getArea(shape: Shape): number {
  switch (shape) {
    case 'circle':
      return Math.PI * 2; // Circumference
    case 'square':
      return 4; // Perimeter
    default:
      // This function will never reach this point because all cases are handled
      const exhaustiveCheck: never = shape;
      return exhaustiveCheck;
  }
}
```

---

## Type Aliases vs Interfaces

[Typescript Official Document](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#differences-between-type-aliases-and-interfaces)

---

# Q & A
