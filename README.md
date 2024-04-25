```powershell
$ pnpm lint

> @ lint D:\Projects\repro_pnpm_inconsistent-nobail
> pnpm run --no-bail '/lint:(?:eslint|tsc)/'

. lint:eslint$ eslint --no-config-lookup test.ts
│ D:\Projects\repro_pnpm_inconsistent-nobail\test.ts
│   0:0  warning  File ignored because of a matching ignore pattern. Use "--no-ignore" to disable file ignore settings or use "--no-warn-ignored" to suppress this war…  
│ ✖ 1 problem (0 errors, 1 warning)
└─ Done in 2.2s
. lint:tsc$ tsc --noEmit test.ts
│ test.ts(1,25): error TS2307: Cannot find module 'nowhere' or its corresponding type declarations.
└─ Failed in 2.4s at D:\Projects\repro_pnpm_inconsistent-nobail
$ $LASTEXITCODE
0
```
The last line should be non-0
