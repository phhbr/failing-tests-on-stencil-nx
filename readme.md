Reproducable by

1. init workspace: `npx create-nx-workspace test-for-stencil-nx`
2. adding nxext/stencil: `yarn add @nxext/stencil`
3. generate stencil:library: `nx g @nxext/stencil:library core`
   1. Error:  _ NX   Cannot find module '@nrwl/storybook' _
   2. adding @nrwl/storybook: `yarn add @nrwl/storybook`
   3. generate stencil:library: `nx g @nxext/stencil:library core`
      1. Warnings
        ```code
            warning " > @nxext/stencil@14.0.6" has unmet peer dependency "@nrwl/linter@^14.5.0".
            warning " > @nxext/stencil@14.0.6" has incorrect peer dependency "@nrwl/jest@^14.5.0".
            warning " > @nxext/stencil@14.0.6" has incorrect peer dependency "@nrwl/workspace@^14.5.0".
            warning " > @nxext/stencil@14.0.6" has unmet peer dependency "@nxext/vite@14.0.3".
            warning " > @nxext/stencil@14.0.6" has unmet peer dependency "tsconfig-paths@^3.12.0".
            warning " > @nxext/stencil@14.0.6" has unmet peer dependency "@nxext/vitest@14.0.2".
        ```
4. running tests: `nx run core:test`
   1. Warnings
        ```code
            [ ERROR ]  Please install supported versions of dev dependencies with either npm or yarn.
                npm install --save-dev @types/jest@27.0.3 jest@27.0.3 jest-cli@27.4.5
        ```
    2. Running installation of jest/jest-cli/types: `yarn add -D @types/jest@27.0.3 jest@27.0.3 jest-cli@27.4.5`
5. Re-Running tests: `nx run core:test`
   1. Output
        ```code
            Test Suites: 2 passed, 2 of 3 total
            Tests:       6 passed, 6 total
            Snapshots:   0 total
            Time:        0.93 s
            Ran all test suites.
        ```
