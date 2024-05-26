This crate is an excerpt from the `redismodule-rs` crate which allows for easy testing.


Basic usage:

```rust
let mut con: TestConnection = TestConnection::new("module");
let res: String = redis::cmd("module.cmd")
    .arg(&["arg1", "arg2"])
    .query(&mut con)
    .with_context(|| "failed to run module.cmd")?;
assert_eq!(res, "OK");
```


