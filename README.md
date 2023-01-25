# SpaceXpanse ID

SpaceXpanse ID (*SpeXID*) is an application built on the SpaceXpanse Multiverse platform, that
turns each SpaceXpanse name into a **secure digital identity** similar to
[NameID](https://nameid.org/).

These identities are meant to be used inside the SpaceXpanse Multiverse ecosystem,
e.g. on chat systems or market places in SpaceXpanse games.  They can, however, be
used by any other application as well.  For instance, websites can enable
"login with SpaceXpanse" to use secure, password-less authentication.  Or messaging
systems can use SpaceXpanse identities for the secure exchange of key fingerprints
for end-to-end encryption.

## Overview

From a high-level point of view, XID allows owners of SpaceXpanse names to
**associate metadata** to their names, that **everyone else can read**.
Due to how SpaceXpanse works, **only the owners of names** are able to modify
the data (through the keys in their wallets).  This ensures that the data
can be trusted by everyone.

There are two types of data that can be associated with names at the moment:

- **Signer addresses** can be used to enable authentication within applications.
  These are ordinary SpaceXpanse addresses from the user's wallet; to authenticate with
  an application, their associated private key is used to sign a specific
  message.  A name can have multiple registered signers, for instance for
  SpaceXpanse wallets on different devices.  Certain addresses can be either *global*
  signers (valid generally for all applications), or they can be set
  specifically for certain applications.

- **Crypto addresses** in general (i.e. for other coins or tokens), so that
  assets can be sent on another blockchain *to a SpaceXpanse name*.

We also plan to support this in the future:

- **Fingerprints of encryption keys** can be associated to names as well.
  This allows the secure and trusted exchange of keys, e.g. for signed emails
  ([GPG](https://gnupg.org/)) or messaging ([OTR](https://otr.cypherpunks.ca/)).

## Technical Details

More details can be found in specific documents:

- [XID game](doc/game.md): Details about the game state and move format
  for XID as game on the SpaceXpanse platform.
- [RPC interface](doc/rpc.md): The JSON format for game states and the RPC
  interface of the XID daemon.
- [REST interface](doc/rest.md): The simple REST API that the XID daemon can
  optionally expose.
- [Light mode](doc/light.md): How XID can be run in a "light mode", which is
  just enough to support generating auth credentials and works without the
  need to run a local SpaceXpanse Core.
- [Authentication](doc/auth.md): How the authentication protocol with a signer
  key works.
