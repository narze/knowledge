# TypeScript

## Add custom types for external libraries

Set `typeRoots` in `tsconfig.json`

```text
"typeRoots": [                           
  "src/types", // Custom types goes here
  "node_modules/@types" // Fallback to default @types path
]
```

Create new type file with subdirectory name as the packages name eg. for `wordcut` package : `src/types/wordcut/index.d.ts`

```text
declare module 'wordcut';
```

You can add more types to functions / variables later within `{}`

```text
declare module 'wordcut' {
  function init(): void;
  function cut(s: string): string;
}
```

## Links

- [Typescript confusion: tsconfig.json module, moduleResolution, target & lib explained](https://medium.com/@tommedema/typescript-confusion-tsconfig-json-module-moduleresolution-target-lib-explained-65db2c44b491) - Explain differences between `module` and `target` option in `tsconfig.json`