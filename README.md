# Kovi

Kovi (Kovi Tecnologia S.A.) is a Brazilian mobility company founded in 2018 that rents and subscribes cars to ride-hailing and delivery app drivers across Latin America. It operates a fleet of new (0km) and certified pre-owned vehicles under monthly, annual and pay-per-kilometer plans that bundle maintenance, protection and vehicle documentation, with a purchase option on its Kovi Proprio product.

Kovi serves twelve Brazilian cities — Sao Paulo, Porto Alegre, Belo Horizonte, Florianopolis, Curitiba, Fortaleza, Goiania, Brasilia, Recife, Santos, Campinas and Salvador — plus a Mexican operation at [kovi.mx](https://kovi.mx), and employs more than 1,400 people.

Website: https://www.kovi.com.br — Backed by: prosus-ventures

## API posture

Kovi publishes **no public API program**: no developer portal, no API documentation, no OpenAPI or GraphQL SDL, no SDKs, no sandbox, no changelog and no status page.

It does run a real production API. The Central do Motorista driver app ([motorista.kovi.com.br](https://motorista.kovi.com.br/authentication/)) is a Vue/Quasar SPA whose bundle ships an Apollo GraphQL client pointed at `https://api.kovi.us/graphql` and `https://api.kovi.us/graphql/driver-central`. That endpoint is authentication-gated — an unauthenticated introspection query returns HTTP 401 `{"message":"Unauthorized"}` — so no schema could be captured.

See [`conformance/kovi-conformance.yml`](conformance/kovi-conformance.yml) for the probed API surface, standards conformance and the full gap list.

## Artifacts

| Artifact | File | Method |
|---|---|---|
| Conformance | `conformance/kovi-conformance.yml` | probed |
| Domain security | `security/kovi-domain-security.yml` | probed |
| Well-known | `well-known/kovi-well-known.yml` | searched (none published) |
| llms.txt | `llms/kovi-llms.txt` | generated |
