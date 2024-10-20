# Installation
> `npm install --save @types/depd`

# Summary
This package contains type definitions for depd (https://github.com/dougwilson/nodejs-depd).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/depd.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/depd/index.d.ts)
````ts
/// <reference types="node" />

export = depd;

declare function depd(namespace: string): depd.Deprecate;

declare namespace depd {
    interface Deprecate {
        (message: string): void;
        // eslint-disable-next-line @typescript-eslint/ban-types
        function<T extends Function>(fn: T, message?: string): T;
        property<T extends object>(obj: T, prop: keyof T, message: string): void;
    }

    interface DeprecationError extends Error {
        readonly name: "DeprecationError";
        namespace: string;
        stack: string;
    }
}

declare global {
    namespace NodeJS {
        interface Process {
            addListener(event: "deprecation", listener: (deprecationError: depd.DeprecationError) => void): this;
            emit(event: "deprecation", code: depd.DeprecationError): boolean;
            on(event: "deprecation", listener: (deprecationError: depd.DeprecationError) => void): this;
            once(event: "deprecation", listener: (deprecationError: depd.DeprecationError) => void): this;
            prependListener(event: "deprecation", listener: (deprecationError: depd.DeprecationError) => void): this;
            prependOnceListener(
                event: "deprecation",
                listener: (deprecationError: depd.DeprecationError) => void,
            ): this;
            listeners(event: "deprecation"): depd.DeprecationError[];
        }
    }
}

````

### Additional Details
 * Last updated: Mon, 20 Nov 2023 23:36:24 GMT
 * Dependencies: [@types/node](https://npmjs.com/package/@types/node)

# Credits
These definitions were written by [Zhiyuan Wang](https://github.com/danny8002), and [BendingBender](https://github.com/BendingBender).
