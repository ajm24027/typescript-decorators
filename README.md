# typescript-decorators

### Decorators

TypeScript decorators and method decorators are a way to add metadata to classes, properties, and methods. Metadata is data that describes other data. For example, you could use a decorator to specify that a property is required or that a method should be logged whenever it is called.

#### Decorators

Decorators can be used to:

    Add metadata to classes, properties, and methods: This can be useful for things like logging, validation, or caching.
    Refactor code: Decorators can be used to move logic out of classes and methods, making code easier to read and maintain.
    Create custom functionality: Decorators can be used to create custom functionality that is not available in TypeScript by default.

```typescript
function constructorLogger(constructor: Function) {
  console.log('This is the constructor ', constructor.toString())
}
```

#### Method Decorators

Method decorators are a special type of decorator that can be used to modify the behavior of methods. Method decorators can be used to:

    Intercept method calls: This can be useful for things like logging, validation, or caching.
    Change the arguments or return value of a method: This can be useful for things like currying or partial application.
    Create custom functionality: Method decorators can be used to create custom functionality that is not available in TypeScript by default.

```typescript
function methodLogger(
  target: any,
  methodName: string,
  descriptor: PropertyDescriptor
): PropertyDescriptor {
  const method = descriptor.value

  descriptor.value = (...args: any[]) => {
    console.log('params', args)
    const result = method.apply(this, args)
    console.log(
      'Calling',
      methodName,
      ' with args :  ',
      args,
      ' the result is ',
      result
    )
    return result
  }
  return descriptor
}
```

Decorators are a powerful tool that can be used to improve the flexibility and readability of TypeScript code. If you are working on a large TypeScript project, you should consider using decorators to improve the maintainability of your code.

Here are some examples of how decorators can be used:

    Logging: You can use a decorator to log whenever a method is called. This can be useful for debugging or tracking the execution of your code.
    Validation: You can use a decorator to validate the arguments that are passed to a method. This can help to ensure that your code is only called with valid data.
    Caching: You can use a decorator to cache the results of a method call. This can improve the performance of your code by avoiding unnecessary recalculations.
    Currying: You can use a decorator to curry a method. This can make it easier to use a method with a variable number of arguments.
    Partial application: You can use a decorator to partially apply a method. This can make it easier to use a method with a specific set of arguments.

Decorators are a powerful tool that can be used to improve the flexibility and readability of TypeScript code. If you are working on a large TypeScript project, you should consider using decorators to improve the maintainability of your code.
