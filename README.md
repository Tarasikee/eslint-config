# ESLint Config

This ESLint configuration is for a TypeScript project that uses the Next.js framework and follows some best practices for code quality. 

## Extends

The configuration extends two configurations:

- `next/core-web-vitals`: This extends the Next.js core configuration with rules related to the [Web Vitals](https://web.dev/vitals/) metrics.
- `eslint:recommended`: This extends the recommended set of rules from ESLint.

## Globals

The configuration defines a single global variable `JSX`. This allows the project to use JSX syntax without ESLint raising an error.

## Parser and Plugins

The project uses the TypeScript version of ESLint (`@typescript-eslint`) as the parser and plugin.

## Rules

The configuration sets several rules for coding practices, including:

- Requiring the use of `===` instead of `==`
- Requiring a comma at the end of multiline object and array declarations
- Requiring semicolons to be omitted
- Requiring a line break at the end of the file
- Disallowing multiple empty lines
- Disallowing unused variables
- Requiring the use of single quotes
- Disallowing the use of the Array constructor
- Requiring double quotes for JSX properties
- Allowing only `warn`, `error`, and `info` methods on the console
- Sorting imports

## Overrides

The configuration sets an override for files that contain tests. These files use the [Testing Library](https://testing-library.com/) lint rules, and the `jest` plugin. The `jest/globals` environment is also set to true.


## Example

Here's an example of a TypeScript + React code that would be linted based on the ESLint configuration provided in your 
previous question:

```tsx

import PropTypes from 'prop-types'
import React from 'react'

interface User {
    name: string;
    age: number;
}

const user: User = {
    name: 'John Doe',
    age: 30,
}

console.info(user)

const UserCard: React.FC<User> = ({ name, age }) => {
    return (
        <div>
            <h1>{name}</h1>
            <p>Age: {age}</p>
        </div>
    )
}

UserCard.propTypes = {
    name: PropTypes.string.isRequired,
    age: PropTypes.number.isRequired,
}

export default UserCard


```

This code would be linted according to the rules specified in the ESLint configuration, such as using single quotes for string literals, having no unused variables, using object curly braces with spacing, etc. This code would also be linted according to the sort-imports rule specified in the ESLint configuration.
