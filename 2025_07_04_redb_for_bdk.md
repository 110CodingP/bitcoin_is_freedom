### `redb` for `bdk`

This summer I worked on implementing a persistence backend (`bdk_redb`) for bdk_wallet and bdk_chain structures using redb.
The motivation behind this was that the current persistence mechanism in BDK is based on sqlite which forces some application developers who use redb for their app data to use two types of databases. redb being a pure rust and lightweight would be a great addition to BDK's persistence mechanism.

#### Work Done So Far
Currently `bdk_redb` contains a Store wrapper around a `redb` Database with methods to persist and read BDK structures. Store also implements
`WalletPersister` under the wallet feature flag which allows `bdk_wallet` users to use the Store for persistence. 

#### What's Next?
`bdk_redb` needs to be tested more extensively than the unit tests. For this `bdk_cli` offers a good playground so currently I am working on bringing `bdk_redb` into `bdk_cli`.
