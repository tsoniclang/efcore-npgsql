# @tsonic/efcore-npgsql

TypeScript declarations and CLR binding metadata for the EF Core PostgreSQL
provider (`Npgsql.EntityFrameworkCore.PostgreSQL`) on .NET 10.

This is a generated binding package. It exposes provider APIs to TypeScript and
Tsonic while your workspace references the real NuGet assemblies.

## Install

```bash
npm install @tsonic/efcore-npgsql @tsonic/efcore @tsonic/dotnet @tsonic/core
```

## Use with Tsonic

```bash
tsonic add nuget Npgsql.EntityFrameworkCore.PostgreSQL <version> @tsonic/efcore-npgsql
tsonic restore
```

## Imports

Provider extensions are exported from the generated `Microsoft.EntityFrameworkCore`
namespace facade:

```ts
import { NpgsqlDbContextOptionsBuilderExtensions } from "@tsonic/efcore-npgsql/Microsoft.EntityFrameworkCore.js";
```

Use EF Core base types from `@tsonic/efcore`:

```ts
import { DbContextOptionsBuilder } from "@tsonic/efcore/Microsoft.EntityFrameworkCore.js";
```

## UseNpgsql example

```ts
import { DbContextOptionsBuilder } from "@tsonic/efcore/Microsoft.EntityFrameworkCore.js";
import { NpgsqlDbContextOptionsBuilderExtensions } from "@tsonic/efcore-npgsql/Microsoft.EntityFrameworkCore.js";

const builder = new DbContextOptionsBuilder();
NpgsqlDbContextOptionsBuilderExtensions.UseNpgsql(builder, "Host=localhost;Database=app;Username=postgres;Password=postgres");
const options = builder.Options;
```

## Package shape

The package contains generated namespace facades, ESM stubs, internal
declarations, extension buckets, and `bindings.json` compiler metadata. It uses
`@tsonic/efcore`, `@tsonic/microsoft-extensions`, `@tsonic/dotnet`, and
`@tsonic/core` as peer packages for shared CLR types.

## Versioning

This repo is versioned by .NET major:

- .NET 10 → npm: `@tsonic/efcore-npgsql@10.x`

## Development

Regenerate from sibling checkouts:

```bash
npm install
./__build/scripts/generate.sh
```

The generation script requires .NET 10, `../tsbindgen`, `../dotnet`,
`../microsoft-extensions`, and `../efcore`.

## License

MIT
