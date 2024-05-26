## TS Get Started
`npm install typescript --save-dev`
`npx tsc` -- run compiler
## TS Simple Types
There are three main primitives in JavaScript and TypeScript.   
- boolean - true or false values
- number - whole numbers and floating point values
- string - text values like "TypeScript Rocks"
There are also 2 less common primitives used in later versions of Javascript and TypeScript.   
- bigint - whole numbers and floating point values, but allows larger negative and positive numbers than the number type.
- symbol are used to create a globally unique identifier.
```ts
let firstName: string = "Dylan"; // Explicit
let firstName = "Dylan"; // Implicit type assignment are shorter, faster to type, and often used when developing and testing.

let firstName = "Dylan"; // inferred to type string
firstName = 33; // attempts to re-assign the value to a different type --> error
```
`noImplicitAny` as an option in a TypeScript's project `tsconfig.json.`
## TS Special Types
`any` is a type that disables type checking and effectively allows all types to be used.
```ts
let u = true;
u = "string"; // Error: Type 'string' is not assignable to type 'boolean'.
Math.round(u); // Error: Argument of type 'boolean' is not assignable to parameter of type 'number'.

let v: any = true;
v = "string"; // no error as it can be "any" type
Math.round(v); // no error as it can be "any" type
```
`unknown` is a similar, but safer alternative to any. `unknown` is best used when you don't know the type of data being typed. To add a type later, you'll need to cast it.
```ts
let w: unknown = 1;
w = "string"; // no error
w = {
  runANonExistentMethod: () => {
    console.log("I think therefore I am");
  }
} as { runANonExistentMethod: () => void}
// How can we avoid the error for the code commented out below when we don't know the type?
// w.runANonExistentMethod(); // Error: Object is of type 'unknown'.
if(typeof w === 'object' && w !== null) {
  (w as { runANonExistentMethod: Function }).runANonExistentMethod();
}
// Although we have to cast multiple times we can do a check in the if to secure our type and have a safer casting
```
`never` effectively throws an error whenever it is defined. `never` is rarely used, especially by itself, its primary use is in advanced generics.
```ts
let x: never = true; // Error: Type 'boolean' is not assignable to type 'never'.
```
`undefined` and `null`. These types don't have much use unless `strictNullChecks` is enabled in the `tsconfig.json` file.
## TS Arrays
```ts
const names: string[] = [];
names.push("Dylan"); // no error
// names.push(3); // Error: Argument of type 'number' is not assignable to parameter of type 'string'.

const names: readonly string[] = ["Dylan"];
names.push("Jack"); // Error: Property 'push' does not exist on type 'readonly string[]'.
// try removing the readonly modifier and see if it works?
```
## TS Tuples
```ts
// define our tuple
let ourTuple: [number, boolean, string];
// initialize correctly
ourTuple = [5, false, 'Coding God was here'];
// We have no type safety in our tuple for indexes 3+
ourTuple.push('Something new and wrong');
console.log(ourTuple);

// define our readonly tuple
const ourReadonlyTuple: readonly [number, boolean, string] = [5, true, 'The Real Coding God'];
// throws error as it is readonly.
ourReadonlyTuple.push('Coding God took a day off');
```
## TS Object Types
```ts
const car: { type: string, mileage: number } = { // Error: Property 'mileage' is missing in type '{ type: string; }' but required in type '{ type: string; mileage: number; }'.
  type: "Toyota",
};
car.mileage = 2000;

const car: { type: string, mileage?: number } = { // no error
  type: "Toyota"
};
car.mileage = 2000;

// Index signatures
const nameAgeMap: { [index: string]: number } = {};
nameAgeMap.Jack = 25; // no error
nameAgeMap.Mark = "Fifty"; // Error: Type 'string' is not assignable to type 'number'.
```
## TS Enums
```ts
enum CardinalDirections {
  North,
  East,
  South,
  West
}
let currentDirection = CardinalDirections.North;
// logs 0
console.log(currentDirection);
// throws error as 'North' is not a valid enum
currentDirection = 'North'; // Error: "North" is not assignable to type 'CardinalDirections'.

enum CardinalDirections {
  North = 'North',
  East = "East",
  South = "South",
  West = "West"
};
// logs "North"
console.log(CardinalDirections.North);
// logs "West"
console.log(CardinalDirections.West);

enum StatusCodes {
  NotFound = 404,
  Success = 200,
  Accepted = 202,
  BadRequest = 400
}
// logs 404
console.log(StatusCodes.NotFound);
// logs 200
console.log(StatusCodes.Success);
```
## TS Aliases & Interfaces
Type Aliases allow defining types with a custom name (an Alias). Type Aliases can be used for primitives like `string` or more complex types such as `objects` and `arrays`   
```ts
type CarYear = number
type CarType = string
type CarModel = string
type Car = {
  year: CarYear,
  type: CarType,
  model: CarModel
}

const carYear: CarYear = 2001
const carType: CarType = "Toyota"
const carModel: CarModel = "Corolla"
const car: Car = {
  year: carYear,
  type: carType,
  model: carModel
};
```
Interfaces are similar to type aliases, except they only apply to `object` types. Interfaces can extend each other's definition.
```ts
interface Rectangle {
  height: number,
  width: number
}

const rectangle: Rectangle = {
  height: 20,
  width: 10
};

interface ColoredRectangle extends Rectangle {
  color: string
}

const coloredRectangle: ColoredRectangle = {
  height: 20,
  width: 10,
  color: "red"
};
```
## TS Union Types
Using the `|` we are saying our parameter is a string or number
```ts
function printStatusCode(code: string | number) {
  console.log(`My status code is ${code.toUpperCase()}.`) // error: Property 'toUpperCase' does not exist ontype 'string | number'.
  Property 'toUpperCase' does not exist on type 'number'
}
```
## TS Functions
```ts
// the `: number` here specifies that this function returns a number
function getTime(): number {
  return new Date().getTime();
}

function printHello(): void {
  console.log('Hello!');
}

// the `?` operator here marks parameter `c` as optional
function add(a: number = 10, b: number, c?: number) {
  return a + b + (c || 0);
}

// named parameters
function divide({ dividend, divisor }: { dividend: number, divisor: number }) {
  return dividend / divisor;
}

// rest parameters 
function add(a: number, b: number, ...rest: number[]) {
  return a + b + rest.reduce((p, c) => p + c, 0);
}

type Negate = (value: number) => number;

// in this function, the parameter `value` automatically gets assigned the type `number` from the type `Negate`
const negateFunction: Negate = (value) => value * -1;
```
## TS Casting
```ts
let x: unknown = 4;
console.log((x as string).length); // prints undefined since numbers don't have a length. Casting doesn't actually change the type of the data within the variable

let x: unknown = 'hello';
console.log((<string>x).length);
// This type of casting will not work with TSX, such as when working on React files.

// force casting
let x = 'hello';
console.log(((x as unknown) as number).length); // x is not actually a number so this will return undefined
```
## TS Classes
There are three main visibility modifiers in TypeScript.   
- public - (default) allows access to the class member from anywhere
- private - only allows access to the class member from within the class
- protected - allows access to the class member from itself and any classes that inherit it, which is covered in the inheritance section below
```ts
class Person {
  private name: string;

  public constructor(name: string) {
    this.name = name;
  }

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName()); // person.name isn't accessible from outside the class since it's private

// name is a private member variable
  public constructor(private name: string) {}

private readonly name: string;
public constructor(name: string) {
  // name cannot be changed after this initial definition, which has to be either at it's declaration or in the constructor.
  this.name = name;
}

interface Shape {
  getArea: () => number;
}

class Rectangle implements Shape {
  // using protected for these members allows access from classes that extend from this class, such as Square
  public constructor(protected readonly width: number, protected readonly height: number) {}

  public getArea(): number {
    return this.width * this.height;
  }

  public toString(): string {
    return `Rectangle[width=${this.width}, height=${this.height}]`;
  }
}

class Square extends Rectangle {
  public constructor(width: number) {
    super(width, width);
  }

  // this toString replaces the toString from Rectangle
  public override toString(): string {
    return `Square[width=${this.width}]`;
  }
}

abstract class Polygon {
  public abstract getArea(): number;

  public toString(): string {
    return `Polygon[area=${this.getArea()}]`;
  }
}

class Rectangle extends Polygon {
  public constructor(protected readonly width: number, protected readonly height: number) {
    super();
  }

  public getArea(): number {
    return this.width * this.height;
  }
}
```
## TS Basic Generics
```ts
function createPair<S, T>(v1: S, v2: T): [S, T] {
  return [v1, v2];
}
console.log(createPair<string, number>('hello', 42)); // ['hello', 42]

class NamedValue<T = string> {
  private _value: T | undefined;

  constructor(private name: string) {}

  public setValue(value: T) {
    this._value = value;
  }

  public getValue(): T | undefined {
    return this._value;
  }

  public toString(): string {
    return `${this.name}: ${this._value}`;
  }
}

let value = new NamedValue('myNumber');
value.setValue('myValue');
console.log(value.toString()); // myNumber: myValue

type Wrapped<T> = { value: T };
const wrappedValue: Wrapped<number> = { value: 10 };

function createLoggedPair<S extends string | number, T extends string | number>(v1: S, v2: T): [S, T] {
  console.log(`creating pair: v1='${v1}', v2='${v2}'`);
  return [v1, v2];
}
```
## TS Utility Types
```ts
interface Point {
  x: number;
  y: number;
}

let pointPart: Partial<Point> = {}; // `Partial` allows x and y to be optional
pointPart.x = 10;

interface Car {
  make: string;
  model: string;
  mileage?: number;
}

let myCar: Required<Car> = {
  make: 'Ford',
  model: 'Focus',
  mileage: 12000 // `Required` forces mileage to be defined
};

// Record is a shortcut to defining an object type with a specific key type and value type.
const nameAgeMap: Record<string, number> = { // Record<string, number> is equivalent to { [key: string]: number }
  'Alice': 21,
  'Bob': 25
};


interface Person {
  name: string;
  age: number;
  location?: string;
}

const bob: Omit<Person, 'age' | 'location'> = {
  name: 'Bob'
  // `Omit` has removed age and location from the type and they can't be defined here
};

interface Person {
  name: string;
  age: number;
  location?: string;
}

const bob: Pick<Person, 'name'> = {
  name: 'Bob'
  // `Pick` has only kept name, so age and location were removed from the type and they can't be defined here
};

type Primitive = string | number | boolean
const value: Exclude<Primitive, string> = true; // a string cannot be used here since Exclude removed it from the type.

type PointGenerator = () => { x: number; y: number; };
const point: ReturnType<PointGenerator> = {
  x: 10,
  y: 20
};

type PointPrinter = (p: { x: number; y: number; }) => void;
const point: Parameters<PointPrinter>[0] = {
  x: 10,
  y: 20
};

interface Person {
  name: string;
  age: number;
}
const person: Readonly<Person> = {
  name: "Dylan",
  age: 35,
};
person.name = 'Israel'; // prog.ts(11,8): error TS2540: Cannot assign to 'name' because it is a read-only property.
```
## TS Keyof
```js
interface Person {
  name: string;
  age: number;
}
// `keyof Person` here creates a union type of "name" and "age", other strings will not be allowed
function printPersonProperty(person: Person, property: keyof Person) {
  console.log(`Printing person property ${property}: "${person[property]}"`);
}
let person = {
  name: "Max",
  age: 27
};
printPersonProperty(person, "name"); // Printing person property name: "Max"

type StringMap = { [key: string]: unknown };
// `keyof StringMap` resolves to `string` here
function createStringPair(property: keyof StringMap, value: string): StringMap {
  return { [property]: value };
}
```
## TS Null
When `strictNullChecks` is enabled, TypeScript requires values to be set unless `undefined` is explicitly added to the type.
```ts
let value: string | undefined | null = null;
value = 'hello';
value = undefined;

// Optional Chaining
interface House {
  sqft: number;
  yard?: {
    sqft: number;
  };
}
function printYardSize(house: House) {
  const yardSize = house.yard?.sqft;
  if (yardSize === undefined) {
    console.log('No yard');
  } else {
    console.log(`Yard is ${yardSize} sqft`);
  }
}

let home: House = {
  sqft: 500
};

printYardSize(home); // Prints 'No yard'

// Nullish Coalescence
function printMileage(mileage: number | null | undefined) {
  console.log(`Mileage: ${mileage ?? 'Not Available'}`);
}

printMileage(null); // Prints 'Mileage: Not Available'
printMileage(0); // Prints 'Mileage: 0'


// Null Assertion. Just like casting, this can be unsafe and should be used with care.
function getValue(): string | undefined {
  return 'hello';
}
let value = getValue();
console.log('value length: ' + value!.length);
```
Even with strictNullChecks enabled, by default TypeScript will assume array access will never return undefined (unless undefined is part of the array type).

The config noUncheckedIndexedAccess can be used to change this behavior.
```ts
let array: number[] = [1, 2, 3];
let value = array[0]; // with `noUncheckedIndexedAccess` this has the type `number | undefined`
```
## TS Definitely Typed
Definitely Typed is a project that provides a central repository of TypeScript definitions for NPM packages which do not have types.

`npm install --save-dev @types/jquery`
## TS 5 Updates
## TS Editor
## TS Exercises
## TS Quiz
## TS Certificate