# Jiaxin-week4-mini-repo

This demo is about building a simple Marco Polo game based on Rust. 

## Game Rule:
One person is selected as "it". Using only hearing, that player searches for and tags any other player they can find while keeping their eyes closed. The other players must all shout "Polo" in response to the "it" player's shout of "Marco," which he or she will use to try to locate them. When a player is tagged, that player takes on the role of "it."

## Prepration
1. Set virtual environment: 
* `python3 -m venv env`
* `source env/bin/activate`

2. Install rust: 
* `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
* `source "$HOME/.cargo/env"`

3. Create new project:
*  `cargo new src` (src is the project name)
* `cargo run`

## Check format and test errors:
1. Format code: `make format`
2. Test code: `make lint`

## Cargo lambda
Within a Rust project that includes a Cargo.toml file, run the cargo lambda build command to natively compile your Lambda functions in the project. 

* `make release-arm` to build for arm which is: cargo lambda build --release --arm64
* `make deploy` for cargo lambda deploy

eg. my results:

```bash
(.venv) @helenyjx ➜ /workspaces/Jiaxin-week4-mini-repo (main) $ make invoke
cargo lambda invoke --remote \
                --data-ascii '{"name": "Marco"}' \
                --output-format json \
                marco-polo-lambda
{
  "msg": "Marco says Polo",
  "req_id": "abc67e2b-a3aa-47fa-98fb-d07eb627577e"
}
```
### References

https://github.com/nogibjj/rust-mlops-template
