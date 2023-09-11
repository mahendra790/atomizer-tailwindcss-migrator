# atomizer-tailwindcss-migrator

CLI tool to refactor atomizer codebases to tailwindcss

Usage

for help

```bash
tw-mg -h
```

Lets say we have our atomizer css class at path `src/styles/main.css` and we want to transform all components under `src/components/atoms/`

```bash
tw-mg -s src/styles/main.css -t "src/components/atoms/*.js"
```

For dry run -- it will only generate report and open it

```bash
tw-mg -s src/styles/main.css -t "src/components/atoms/*.js" --dry-run
```

If you want to replace atomizer variables name with other names in tailwind you can pass json file with mapping from atomic var to tailwind var

Eg: mappings.json

```json
{
  "fzTitle": "title",
  "$someLongCamelCase": "short-snake-case"
}
```

it will replace var `fzTitle` with `title` and so on.

```bash
tw-mg -s src/styles/main.css -t "src/components/atoms/*.js" -m 'mappings.json' -d
```

If you do not want to open the report by default

```bash
tw-mg -s src/styles/main.css -t "src/components/atoms/*.js" -d -no
```

after running these a `transform-report.html` will be generated and opened in browser which will contain all the details.
