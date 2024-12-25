### Anonymous RPC

This will spin up a proxy that gives you free anonymous access to RPC endpoints for popular blockchains at http://localhost:9296.

Because it's anonymous it's slow. Rountrips take about 10-20 seconds. The proxy is build using cmix from https;//xx.network.


### Intallation

To run you need *docker* installed.

```
git clone squidfura
cd squidfura
echo "PASSWORD=mycreativepassword" > .env
docker compuse up -d
```

You can test after a few seconds using curl.

```
http://localhost:9296/ronin/mainnet \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":1}'
```

### Usage

This gives you a REST endpoint for a bunch of chains. You can spot them on startup in the logs of the container.

```
docker logs -f squidfura-client-1
```
You should see the following.

```
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/telos/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/telos/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/celo/alfajores
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/celo/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/goat_network/mainnet_alpha
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/goat_network/testnet3
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zora/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zora/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/dymension/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/rootstock/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/rootstock/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/haqq/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/haqq/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/cosmos_hub/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/cosmos_hub/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kroma/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kroma/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/moonriver/moonriver
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/wemix/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/wemix/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/blast/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/blast/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/gameswift/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zetachain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zetachain/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bnb_smart_chain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bnb_smart_chain/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bitcoin/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bitcoin/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zksync_era/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zksync_era/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zircuit/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zircuit/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/fuse/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/thundercore/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/thundercore/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/fraxtal/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/fraxtal/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ronin/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ronin/saigon
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/apechain/curtis
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/apechain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/sonic/blaze_testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/sonic/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/aurora/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/aurora/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/neutron/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/neutron/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/solana/devnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/solana/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/solana/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/metal_l2/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/metal_l2/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kava/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kava/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/op_celestia_raspberry/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/base/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/base/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/avail/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/avail/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/linea/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/linea/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/polkadot/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/neon_evm/devnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/neon_evm/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/worldchain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/worldchain/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/mode/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/mode/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/core/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/core/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/zero_network/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/taiko/hekla
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/taiko/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/optimism/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/optimism/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kusama/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/filecoin/calibration_testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/filecoin/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/axelar/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/axelar/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/cronos/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/cronos/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/aleph_zero_network/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/aleph_zero_network/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/moonbeam/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/moonbeam/moonbase_alpha
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/scroll/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/scroll/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/manta_network/manta_pacific_mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/manta_network/manta_pacific_sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/metis/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/metis/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kaia/baobab
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/kaia/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/near/betanet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/near/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/near/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/avalanche/fuji
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/avalanche/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ethereum/holesky
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ethereum/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ethereum/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/okt_chain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/okt_chain/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bob/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bob/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/snaxchain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/snaxchain/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/opbnb/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/opbnb/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ethereum_beacon_chain/holesky
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ethereum_beacon_chain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ethereum_beacon_chain/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/real/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/open_campus_codex/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/sei/devnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/sei/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/sei/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/boba_ethereum/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/arbitrum_one/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/arbitrum_one/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/heco/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/heco/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ton/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/ton/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/polygon/amoy
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/polygon/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/unichain/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/unichain/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/fantom/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/fantom/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/polygon_blackberry/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/immutable_zkevm/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/immutable_zkevm/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/cronos_zkevm/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/cronos_zkevm/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/soneium/minato
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/arbitrum_blueberry/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/gnosis/chiado
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/gnosis/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/vara_network/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/vara_network/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/evmos/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/evmos/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/harmony/mainnet_shard_0
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/harmony/mainnet_shard_1
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/osmosis/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/osmosis/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/berachain/bartio
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/polygon_zkevm/cardona
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/polygon_zkevm/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/tron/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/tron/shasta
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/lisk/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/lisk/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/mantle/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/mantle/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/arbitrum_nova/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/playnance/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/playnance/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/viction/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/viction/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/xlayer/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/xlayer/testnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/everclear/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/everclear/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/boba_bnb/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/starknet/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/starknet/sepolia
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bittorrent/mainnet
INFO 2024/12/25 09:08:35 [RELAY] http://localhost:9296/bittorrent/testnet
```

### Merry Christmas

