## What is the use of the keyof keyword in TypeScript? Provide an example.

Answer:
The keyof operator in TypeScript is used to derive new types from an existing object type's keys. This allows for type-safe access to object properties and can be particularly useful when working with generic types or when needing to constrain the keys that can be used to access an object.

==> Example:

```interface Person {
name: string;
age: number;
location: string;
}

type PersonKeys = keyof Person;

function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
return obj[key];
}

const person: Person = {
name: "Kawsar",
age: 25,
location: "Bangladesh",
};

const personName: string = getProperty(person, "name");
const personAge: number = getProperty(person, "age");
const personLocation: string = getProperty(person, "location");
```

## Provide an example of using union and intersection types in TypeScript

Answer:

###

A union type means a value can be one of several types.

```
type Status = "success" | "error" | "loading";

let currentStatus: Status;

currentStatus = "success";
currentStatus = "error";
```

### Intersection

An intersection type combines multiple types into one. A value must satisfy all the types.

```
type User = {
  name: string;
};

type Admin = {
  role: string;
};

type AdminUser = User & Admin;

const admin: AdminUser = {
  name: "Alice",
  role: "superadmin",
};

```
