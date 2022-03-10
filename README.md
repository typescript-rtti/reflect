# `reflect`
[![Version](https://img.shields.io/npm/v/@typescript-rtti/reflect.svg)](https://www.npmjs.com/package/@typescript-rtti/reflect)
[![CircleCI](https://circleci.com/gh/typescript-rtti/reflect/tree/main.svg?style=shield)](https://circleci.com/gh/typescript-rtti/reflect/tree/main)

## Unified Reflection

This is a project to separate [typescript-rtti](https://github.com/typescript-rtti/typescript-rtti)'s reflection library
into an independent library and implement other metadata formats. Currently supports `emitDecoratorMetadata` 
and `typescript-rtti`.

# Usage

```
npm install @typescript-rtti/reflect
```

Traditional metadata (`emitDecoratorMetadata`):

```typescript
import { reflect } from '@typescript-rtti/reflect';

@dec() class A { 
    constructor(str : string, num : number) {
    }
}

expect(reflect(A).parameters[0].type.isClass(String)).to.be.true;
```

`typescript-rtti`

```typescript
import { reflect } from '@typescript-rtti/reflect';

class A {
    constructor(str : string, num : number) {
    }
}

expect(reflect(A).parameters[0].type.isClass(String)).to.be.true;
```