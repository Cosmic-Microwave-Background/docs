# README

## Starport IBC 
https://github.com/tendermint/starport/blob/develop/docs/1%20Introduction/6%20Starport%20IBC.md

## Hot to get ibc address
rly chains address enf1 --home ~/enf1d/relayer/
rly chains address enf2 --home ~/enf2d/relayer/

## Show chain keys
enf1d keys list --keyring-backend test
enf2d keys list --keyring-backend test

## Check balances
enf1d q bank balances $(enf1d keys show enf1 -a --keyring-backend test)
enf2d q bank balances $(enf2d keys show enf2 -a --keyring-backend test) --node=http://0.0.0.0:26557

## IBC transfer
rly chains list --home ~/enf1d/relayer/
rly tx transfer enf1 enf2 5token $(rly chains address enf2 --home ~/enf1d/relayer/) --home ~/enf1d/relayer/
rly tx relay enf1-enf2 --home ~/enf1d/relayer/
