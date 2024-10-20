# Installation
> `npm install --save @types/find-in-files`

# Summary
This package contains type definitions for find-in-files (https://github.com/kaesetoast/find-in-files).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/find-in-files.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/find-in-files/index.d.ts)
````ts
export interface FindResult {
    [filePath: string]: {
        matches: string[];
        count: number;
        line: string | null;
    };
}

export interface RegexControlOptions {
    term: string;
    flags: string;
}

export function find(
    pattern: string | RegExp | RegexControlOptions,
    directory: string,
    fileFilter?: string | RegExp,
): Promise<FindResult>;
export function findSync(
    pattern: string | RegExp | RegexControlOptions,
    directory: string,
    fileFilter?: string | RegExp,
): FindResult;

````

### Additional Details
 * Last updated: Tue, 07 Nov 2023 03:09:37 GMT
 * Dependencies: none

# Credits
These definitions were written by [goooseman](https://github.com/goooseman).
