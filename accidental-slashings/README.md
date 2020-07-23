Problem:

> Dankrad: Starting a validator client for the same validator twice is of course a user error. However, it's probably the most common user error that leads to slashing. If the two clients are started at the same time, there is no way to catch this error; however, in all other cases, the second client being started can detect that the last attestation made by the validator does not match its local storage, and refuse operation (without an override flag).

Suggested solution:

> Dankrad: add a BN API endpoint to query for the latest attestation by a given validator index VC queries this endpoint on startup, if it does not match local storage, stops with warning


See [original issue](https://github.com/ethereum/eth2.0-APIs/issues/64) here.

See the discussion in [this issue](https://github.com/PegaSysEng/teku/issues/1887) too.

> Benjaminion: The idea is not to rely solely on a validator's own journal of its history. The beacon node it is attached to sees what's on the network and will know if there is some other validator out there using the same public key by looking at what gets into blocks.
