# Reflection

**Lightweight metadata reflection api**

> This module is a extended version of [@abraham/reflection](https://github.com/abraham/reflection).

## Extended Methods :

- `Reflect.getOwnMetadataKeys`

```typescript
const target = { property: "propValue" };
Reflect.defineMetadata("firstKey", "firstValue", target);
Reflect.defineMetadata("secondKey", "secondValue", target);

Reflect.defineMetadata("firstPropKey", "firstPropValue", target, "property");
Reflect.defineMetadata("secondPropKey", "secondPropValue", target, "property");

Reflect.getOwnMetadataKeys(target);
// Result => ["firstKey", "secondKey" ]

console.log(Reflect.getOwnMetadataKeys(target));
// Result => ["firstKey", "secondKey" ]
console.log(Reflect.getOwnMetadataKeys(target, "property"));
// Result => ["firstPropKey", "secondPropKey" ]
```
- `Reflect.getMetaDataKey`
```typescript
class Parent {}
class Child extends Parent {}

Reflect.defineMetadata("key", "value", Parent);
Reflect.defineMetadata("propKey", "propValue", Parent, "property");

console.log(Reflect.getMetadataKeys(Child));
//Result => ["key" ]

console.log(Reflect.getMetadataKeys(Child, "property"));
//Result => ["propKey" ]
```