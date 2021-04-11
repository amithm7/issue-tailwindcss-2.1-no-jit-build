# issue-tailwindcss-2.1-no-jit-build

With TailwindCSS 2.1.1, when JIT mode is disabled, and using extended variants, precedence is of classes are not properly compiled.

For example, here 'dark' variant is extended with 'display'.

And with JIT disabled, compiled in production environment, `.hidden { display: none }` class has higher precedence than `@media (prefers-color-scheme: dark) { .dark\:block { display: block }}`.

However with JIT enabled (see ./build-styles-jit.css), this issue doesn't exist. (Extended variants are not needed here anyway)
