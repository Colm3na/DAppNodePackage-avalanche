This package contains an Avalanche Node and a local WalletUI

The **Wallet UI** is accesible through: [avalanche.public.dappnode](http://avalanche.public.dappnode/). Keep in mind that even though this is an HTTP gateway, as long as you're connected through VPN to your DAppNode you'll be in a safe connection.

⚠️ **Important**: You will have to wait for your node to synchronize to connect the wallet UI to your node. Your wallet might not work until then. To see the progress on the synchronization of your node check the logs [here](http://my.dappnode/#/packages/avalanche.public.dappnode.eth/logs).

⚠️ Please note that this WalletUI is a [clone](https://github.com/ava-labs/avalanche-wallet.git) of the Avalanche Wallet, and it is expected to display a warning on the top saying "Make sure the URL is wallet.avax.network". The correct link for the local DAppNode Avalanche Wallet is "http://avalanche.public.dappnode/".

If you prefer to run the public [Avalanche Wallet](https://wallet.avax.network/), you can connect to your DAppNode Avalanche node with the `nodeID` you can find in the [logs](http://my.dappnode/#/packages/avalanche.public.dappnode.eth/logs).
