# `faker-create-factory`

🏭 Factory creator utility to Faker.js

[![Build Status](https://circleci.com/gh/lffg/faker-create-factory.svg?style=svg)](https://circleci.com/gh/lffg/faker-create-factory)
[![NPM](https://img.shields.io/npm/v/faker-create-factory.svg?logo=npm)](https://npmjs.org/package/faker-create-factory)
![Uses TypeScript](https://img.shields.io/badge/Uses-Typescript-294E80.svg)

## Installing

```shell
yarn add faker faker-create-factory

# If you're using NPM:
# npm install faker faker-create-factory
```

## Basic Usage

```typescript
import { createFactory } from 'faker-create-factory';

export const UserFactory = createFactory<User>((faker) => ({
  id: faker.random.uuid(),
  email: faker.internet.email(),
  username: faker.internet.userName(),
  password: '123'
}));

// And the use it as:
UserFactory.generate(); // User
UserFactory.generateMany(5); // Array<User>
```

If needed, you can override the default schema:

```typescript
import { createFactory } from 'faker-create-factory';

export const Factory = createFactory<Interface>((faker) => ({
  // ...
}));

// Plain object:
Factory.generate({
  // ...
});

// With a faker instance:
Factory.generateMany(5, (faker) => {
  // ...
});
```

The two options (_plain object_ and _with a faker instance_) described above are available in both `generate` and `generateMany` methods.

## Authors and License

[lffg](https://github.com/lffg) and [contributors](https://github.com/lffg/faker-create-factory/graphs/contributors).

MIT License, see the included [MIT](https://github.com/lffg/faker-create-factory/blob/master/LICENSE) file.
