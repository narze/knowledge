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

