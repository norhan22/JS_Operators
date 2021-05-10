
# JS Opertaors 

## [**Nullish coalescing operator (??)**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)
It is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand.


_Ex :_

    let myText = ''; // An empty string (which is also a falsy value)
    let notFalsyText = myText || 'Hello world';
    console.log(notFalsyText); // Hello world

    let preservingFalsy = myText ?? 'Hi neighborhood';
    console.log(preservingFalsy); // '' (as myText is neither undefined nor null)



**The Main diff between ?? and ||** 

- **|| =>** any  of the falsy value (0, '', NaN, null, undefined) won't return 
- **?? =>** only  null && undefined won't return 

**** 

## [**Optional chaining (?.)**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)

It is like the _**. chaining operator**_, except that instead of causing an error if a reference is nullish (null or undefined),


_usage :_
 - Property : 
    - before   :` obj.first && obj.first.second; `
    - after:  `obj.first?.second` ( if false will reurn undefined )     // no exception if  obj.first is undefined
 - Method :
    - before : `if (onError) { onError(err.message);  }  // Testing if onError really exists`
    - after :  `onError?.(err.message); // no exception if onError is undefined`
    
    
_Ex :_

    let arrayItem = arr?.[42];   // access that arr item valye
    let customerCity = customer.details?.address?.city;    // With nested structures, it is possible to use optional chaining multiple times:



_Advanced Ex:_

    let customer = {
      name: "Carl",
      details: { age: 82 }
    };
    const customerCity = customer?.city ?? "Unknown city";
    console.log(customerCity); // Unknown city



**Note :** Optional chaining (?.) not valid on the left-hand side of an assignment

    let object = {};
    object?.property = 1; // Uncaught SyntaxError: Invalid left-hand side in assignment
