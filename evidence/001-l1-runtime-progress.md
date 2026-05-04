# 001 — L1 Runtime Progress

## What this note is

This note provides a sanitized public evidence sample related to NewGen L1 runtime progress.

It focuses on observable behavior during validation: snapshot export activity, peer-delivered block intake, local tip extension, fee-controller observation fields, and steady-state sync behavior.

This is not a mainnet launch claim, a public testnet announcement, or an open onboarding notice.

## Scope

This note covers:

- NewGen L1 block progression
- block intake from a peer
- local chain tip extension
- steady-state node operation
- empty mempool pressure observation
- checkpoint/bootstrap snapshot export activity

## Sanitized runtime excerpt

The following excerpt is taken from a NewGen L1 validation run.

Peer identifiers and block hashes are shortened. Event names, timestamps, heights, node labels, runtime states, fee-controller observation fields, and snapshot metadata are preserved.

```text
ts=1777931850947 level=INFO node=A target=snapshot.export event=snapshot_export_summary node=A bundle_count=1 bundles=checkpoint-latest@height=461,window_from=0,chunks=8,reachable_only=true
ts=1777931879451 level=INFO node=A target=snapshot.export event=snapshot_export_summary node=A bundle_count=1 bundles=bootstrap-latest@height=461,window_from=0,chunks=8,reachable_only=true

ts=1777931880477 level=INFO node=A target=p2p.chain event=newblock_extends_tip height=462
ts=1777931880478 level=INFO node=A target=eco.ctrl event=fill_estimation_source height=462 source=user_tx_primary fill_ppm=0 ema_fill_ppm=0 mempool_before=0 mempool_after=0 eligible_before=0 eligible_after=0 selected_txs=0 recent_admitted=0 recent_fee_low_rejected=0 recent_fee_low_pruned=0 recent_ingress=0 stale_backlog_hold=false pressure_mempool_len=0
ts=1777931880483 level=INFO node=A target=p2p.chain event=new_block_intake state=applied block_hash=01fc1f93...85558d53 block_height=462 prev_hash=5b0bb735...d6bcc13 sender_peer=12D3KooW...ERjKRn local_height=462 disposition=applied reason_code=tip_extend boot_phase=steady_state sync_state=idle
ts=1777931880969 level=INFO node=A target=snapshot.export event=snapshot_export_summary node=A bundle_count=1 bundles=checkpoint-latest@height=462,window_from=0,chunks=8,reachable_only=true

ts=1777931910472 level=INFO node=A target=p2p.chain event=newblock_extends_tip height=463
ts=1777931910473 level=INFO node=A target=eco.ctrl event=fill_estimation_source height=463 source=user_tx_primary fill_ppm=0 ema_fill_ppm=0 mempool_before=0 mempool_after=0 eligible_before=0 eligible_after=0 selected_txs=0 recent_admitted=0 recent_fee_low_rejected=0 recent_fee_low_pruned=0 recent_ingress=0 stale_backlog_hold=false pressure_mempool_len=0
ts=1777931910478 level=INFO node=A target=p2p.chain event=new_block_intake state=applied block_hash=74a7e623...67158ac0b4 block_height=463 prev_hash=01fc1f93...85558d53 sender_peer=12D3KooW...ERjKRn local_height=463 disposition=applied reason_code=tip_extend boot_phase=steady_state sync_state=idle
ts=1777931910947 level=INFO node=A target=snapshot.export event=snapshot_export_summary node=A bundle_count=1 bundles=checkpoint-latest@height=463,window_from=0,chunks=8,reachable_only=true

ts=1777931940017 level=INFO node=A target=eco.ctrl event=fill_estimation_source height=464 source=user_tx_primary fill_ppm=0 ema_fill_ppm=0 mempool_before=0 mempool_after=0 eligible_before=0 eligible_after=0 selected_txs=0 recent_admitted=0 recent_fee_low_rejected=0 recent_fee_low_pruned=0 recent_ingress=0 stale_backlog_hold=false pressure_mempool_len=0
ts=1777931941229 level=INFO node=A target=snapshot.export event=snapshot_export_summary node=A bundle_count=2 bundles=bootstrap-latest@height=464,window_from=0,chunks=8,reachable_only=true;checkpoint-latest@height=464,window_from=0,chunks=8,reachable_only=true
```

## Interpretation

This excerpt shows node `A` receiving and applying consecutive NewGen L1 blocks from a peer during steady-state operation.

The node extends its local tip from height `462` to height `463`, keeps `sync_state=idle`, records empty mempool pressure, and exports checkpoint/bootstrap snapshot bundles with reachable state data.

The `sender_peer` field is intentionally preserved in shortened form to show that the applied blocks were received through the peer-to-peer layer rather than represented as a synthetic local-only trace.

## What this demonstrates

This evidence sample demonstrates observable runtime behavior for NewGen L1 during validation:

- peer-delivered block intake is recorded
- applied blocks extend the local chain tip
- runtime state remains in `steady_state`
- sync state remains `idle` during the observed block application path
- fee-controller observation fields report no mempool pressure in this excerpt
- snapshot export summaries are produced around the observed heights

## What this does not claim

This note does not claim:

- that mainnet is live
- that public tests are currently open
- that validator onboarding is open
- that this is a complete runtime log
- that all internal consensus, networking, or snapshot details are public
- that source code or operational runbooks are being published

## Publication posture

This excerpt is intentionally partial and sanitized.

Local paths, private endpoints, full peer identifiers, full hashes, node secrets, validator material, wallet material, API tokens, and operational runbooks are not included.
