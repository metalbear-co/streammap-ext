# streammap-ext

This is a fork of `StreamMap` from `tokio-stream` (crate)[https://github.com/tokio-rs/tokio/blob/master/tokio-stream/src/stream_map.rs].
The only difference between the implementations is that this version of StreamMap `next` returns `Option<K,Option<V>>` instead of `Option<K,V>`.  This is to allow the developer to be aware when a stream is being dropped from the StreamMap, without the need to implement a `Drop` trait which can be troublesome in some cases (e.g. the drop flow requires async code).

After releasing this crate, I'll open a discussion to consider how to contribute it back to the original crate (as a different name, maybe a PhantomData that marks behavior, or maybe change the current behavior to this).

# LICENSE
MIT - Same as source, all copy right goes to Tokio Contributors as this is a fork of `tokio-stream` crate.