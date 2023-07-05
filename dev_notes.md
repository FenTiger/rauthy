# Internal development notes

## Build

To build the project, a few things have to be done:
- `cd frontend`
- `npm install`
- `./build.sh`
- `cd ..`
- Rauthy Dev Build: `cargo build` - Prod Build: `cargo build --release`

## Testing

### Install Dependencies

TODO

### Execute tests:

start the backend:

`cargo run test`

in another terminal:

`cargo test`

## TODO List

### CURRENT WORK

### Stage 1 - essentials

[x] finished

### Stage 2 - features - do before v1.0.0

- add more documentation
- cleanup
- check why DB migration returned an error inside OCI Pods only (and nowhere else)
- possible improvement: test if it makes a difference and maybe initialize argon2 hasher only once
- benchmarks and performance tuning

### Stage 3 - Possible nice to haves

- UI translation (account / login page)?
- add temporary users
- auto-encrypted backups + backups to remote locations (ssh, nfs, s3, ...) -> postponed - should be applied to sqlite only
since postgres has pg_backrest and a lot of well established tooling anyway
- when a user changes his email address, set email to not verified again and send a validation email
- double check against https://openid.net/specs/openid-connect-core-1_0.html that everything is implemented correctly one more time
- add all default claims for users https://openid.net/specs/openid-connect-core-1_0.html#ScopeClaims
- oidc-client (google, github, ...)
- 'rauthy-migrate' project to help migrating to rauthy?
- add mysql?
- add tracing-actix-web + opentelemetry
- observe the svelte issue about the necessary 'unsafe-inline' CSP --> update: should be fixed with svelte 4
- NATS events stream or maybe internal one?
- store MFA App secrets encrypted?
- PoW verification can potentially be performance optimized with 1 less allocation per iteration