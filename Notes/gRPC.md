
A type of [[RPC (Remote Procedure Call)]] interface.

## Key Feature

*Protocol buffers*, a binary protocol used in a similar way to [[JSON]] from a front standpoint, used for sending [[HTTP]] payloads like a [[REST]] API.

Basically you create structured pieces of data like objects and define rpc services which can be called (a la functions) in special proto files, this is then all callable via service calls over HTTP.

![Concept Diagram](https://grpc.io/img/landing-2.svg)

See also:
- https://www.youtube.com/watch?v=_4TPM6clQjM