# NewGen L1 — Node B Clean-DB Snapshot Bootstrap Evidence

Generated at: 2026-06-18 22:28:30 UTC

## Summary

Node B runtime state was reset while preserving config and keystore. On restart, Node B began from local_height=0, detected a large gap against live peers, entered ColdStartSnapshot, requested snapshot metadata over RRv3, restored snapshot state, completed state sync, transitioned to SteadyState, and rejoined the live node set, with repeated follow-up checks confirming A/B/C height/finality/hash alignment.

## 1. Preserved identity/config

```text
[OK] nodeB/config/secrets/keystore.json present
[OK] nodeB/data/config/secrets/keystore.json present
```

## 2. Node B starts from local_height=0 and enters ColdStartSnapshot

```text
ts=1781818575442 level=INFO node=B target=p2p.snapshot   [BOOTSTRAP-NUDGE] phase=ColdStartSnapshot requeued=0 immediate_dials=1 connected=0 hello_ok=0 adverts=0
ts=1781818575442 level=DEBUG node=B target=p2p.misc   Nuovo indirizzo in ascolto confermato: /ip4/127.0.0.1/tcp/7002
ts=1781818575442 level=DEBUG node=B target=p2p.misc   Nuovo indirizzo in ascolto confermato: /ip4/65.109.xxx.xxx/tcp/7002
ts=1781818575444 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_blocked_deferred_retry local_height=0 peer_height=0 gap=0 boot_phase=ColdStartSnapshot deferred_queue=0 reason=large_gap_snapshot_required
ts=1781818575444 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=deferred_retry local_height=0 peer_height=0 gap=0 boot_phase=ColdStartSnapshot peer=none reason=large_gap_snapshot_required
ts=1781818575444 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=deferred_retry local_height=0 peer_height=0 gap=0 boot_phase=ColdStartSnapshot peer=none reason=supervisor_not_ready action=retry_later
ts=1781818575445 level=DEBUG node=B target=p2p.misc    [P2P] Mining paused (Phase=ColdStartSnapshot Peers=0 Syncing=false Behind=false AnyPeerBehind=false LocalNext=1 MaxKnown=1 PauseCatchup=false ProposalGateOpen=false OutboxBlockPending=false FreshViewOK=true TipGateOK=true (cons=0 miss_tip=0 mism=0 elig=0 k=0) ForkRaw=false ForkHard=false (fork_mismatches=0/fork_considered=0, fork_k=1))
```

## 3. Node B detects large peer gap and snapshot priority is enforced

```text
ts=1781818725193 level=INFO node=B target=p2p.snapshot   [RRV3/SNAPSHOT] bootstrap readiness probe GetSnapshotV2Latest -> peer=12D3KooW...
ts=1781818725319 level=DEBUG node=B target=p2p.misc   Hello ricevuto da 12D3KooW... prima del completamento dell'Hello locale; handshake ancora pending.
ts=1781818725319 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_blocked_sync_arming path=hello local_height=0 peer_height=41665 gap=41665 boot_phase=ColdStartSnapshot reason=large_gap_snapshot_required
ts=1781818725319 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=hello local_height=0 peer_height=41665 gap=41665 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=large_gap_snapshot_required
ts=1781818725319 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=hello local_height=0 peer_height=41665 gap=41665 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=supervisor_not_ready action=retry_later
ts=1781818725743 level=WARN node=B target=p2p.sync event=rrv3_getheaders_hard_gated peer=12D3KooW... from_height=1 local_height=0 peer_height=41665 boot_phase=ColdStartSnapshot snapshot_priority_blocked=true state_sync_pending=false local_retry_blocked=false sync_in_flight=false
ts=1781818725743 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=rrv3_getheaders local_height=0 peer_height=41665 gap=41665 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=large_gap_snapshot_required
ts=1781818725743 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=rrv3_getheaders local_height=0 peer_height=41665 gap=41665 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=supervisor_not_ready action=retry_later
ts=1781818744643 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=rrv3_getheaders local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=large_gap_snapshot_required
ts=1781818744644 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=rrv3_getheaders local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=supervisor_not_ready action=retry_later
ts=1781818745044 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=deferred_retry local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=none reason=large_gap_snapshot_required
ts=1781818745044 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=deferred_retry local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=none reason=supervisor_not_ready action=retry_later
ts=1781818746287 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_blocked_sync_arming path=hello local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot reason=large_gap_snapshot_required
ts=1781818746287 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=hello local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=large_gap_snapshot_required
ts=1781818746287 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=hello local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=supervisor_not_ready action=retry_later
```

## 4. Node B requests and selects snapshot metadata over RRv3

```text
ts=1781818740194 level=INFO node=B target=p2p.snapshot   [RRV3/SNAPSHOT] runtime ctrl request GetSnapshotV2Latest -> explicit peer=12D3KooW... phase=ColdStartSnapshot
ts=1781818740240 level=INFO node=B target=state_sync.bootstrap event=runtime_bootstrap_meta_selected round=2 rounds=4 rr_successes=1 meta_responses=1 rejected=0 peers_for_bundle=1
```

## 5. Node B restores snapshot state and arms post-snapshot catchup

```text
ts=1781818799811 level=INFO node=B target=storage.boot restored snapshot economy state height=41517 base_height=0 prospective_base_fee_per_tx=100 treasury=8750 total_supply=423127155
ts=1781818799821 level=INFO node=B target=storage.boot restored compute order state store tip=41517 base_height=0 complete_from_genesis=true
ts=1781818800286 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_blocked_sync_arming path=hello local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot reason=large_gap_snapshot_required
ts=1781818800286 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=hello local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=large_gap_snapshot_required
ts=1781818800286 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=hello local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=12D3KooW... reason=supervisor_not_ready action=retry_later
ts=1781818801043 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_trigger_statesync path=deferred_retry local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=none reason=large_gap_snapshot_required
ts=1781818801043 level=WARN node=B target=p2p.sync event=snapshot_priority_gate_statesync_trigger_deferred path=deferred_retry local_height=0 peer_height=41666 gap=41666 boot_phase=ColdStartSnapshot peer=none reason=supervisor_not_ready action=retry_later
ts=1781818801344 level=WARN node=B target=p2p.sync event=rrv3_getheaders_hard_gated peer=12D3KooW... from_height=1 local_height=0 peer_height=41666 boot_phase=ColdStartSnapshot snapshot_priority_blocked=true state_sync_pending=false local_retry_blocked=false sync_in_flight=false
ts=1781818802735 level=INFO node=B target=boot.auth Local miner authorization updated: enabled pubkey=bea2d2a9... reason=validator_set
ts=1781818802735 level=INFO node=B target=p2p.sync StateSyncApplied: reset inflight sync/bootstrap caches; retained live peer observations for 1 connected peers and re-primed local hello broadcast
ts=1781818802735 level=INFO node=B target=p2p.boot   Boot phase transition: ColdStartSnapshot -> RestartCatchup
ts=1781818802738 level=INFO node=B target=p2p.sync event=post_snapshot_catchup_armed phase=RestartCatchup from=41518 connected_peers=1 chosen_peer=12D3KooW...
```

## 6. Node B reaches SteadyState

```text
ts=1781818822140 level=INFO node=B target=runtime.state runtime_sync_caught_up false -> true
ts=1781818822446 level=INFO node=B target=p2p.boot   Boot phase transition: RestartCatchup -> SteadyState (connected=1, hello_ok=1, peer_heights=1, local_next=41666, max_known=41666, syncing=false, mine_behind=false, consensus_context_ready=true)
ts=1781818822446 level=INFO node=B target=runtime.state runtime_bootstrap_complete false -> true
```

## 7. A/B alignment after Node B rejoin; transient C API check

A first API poll showed A/B aligned while port 8003 returned a transient degraded response. The following repeated checks confirmed A/B/C alignment and continued block advancement.

```text
===== port 8001 =====
status= ok
height= 41760
finalized_height= 41758
last_block_hash= dc333c2dd01e57929787884aee3490855259340473344d8c80f580e9522c43d3
finalized_hash= a959e68e829480dd6cff1e2a027fce3957cd7749d1038ccd4c7d911bf2410ec8
runtime_bootstrap_complete= True
runtime_sync_caught_up= True
consensus_ready= True
operational_runtime_quorum_ready= True
p2p_ready_for_mining= True
validator_pubkey= 74c2d9e9...
===== port 8002 =====
status= ok
height= 41760
finalized_height= 41758
last_block_hash= dc333c2dd01e57929787884aee3490855259340473344d8c80f580e9522c43d3
finalized_hash= a959e68e829480dd6cff1e2a027fce3957cd7749d1038ccd4c7d911bf2410ec8
runtime_bootstrap_complete= True
runtime_sync_caught_up= True
consensus_ready= False
operational_runtime_quorum_ready= True
p2p_ready_for_mining= True
validator_pubkey= bea2d2a9...
===== port 8003 =====
status= degraded
height= None
finalized_height= None
last_block_hash= None
finalized_hash= None
runtime_bootstrap_complete= None
runtime_sync_caught_up= None
consensus_ready= None
operational_runtime_quorum_ready= None
p2p_ready_for_mining= None
validator_pubkey= None
```

## 8. A/B/C block advancement after Node B rejoin

```text
===== CHECK 1 Fri Jun 19 12:28:31 AM CEST 2026 =====
port=8001 height=41760 finalized=41758 hash=dc333c2dd01e5792 base_fee=100
port=8002 height=41760 finalized=41758 hash=dc333c2dd01e5792 base_fee=100
port=8003 height=41760 finalized=41758 hash=dc333c2dd01e5792 base_fee=100
===== CHECK 2 Fri Jun 19 12:29:06 AM CEST 2026 =====
port=8001 height=41761 finalized=41760 hash=fa9da9df62875e38 base_fee=100
port=8002 height=41761 finalized=41760 hash=fa9da9df62875e38 base_fee=100
port=8003 height=41761 finalized=41760 hash=fa9da9df62875e38 base_fee=100
```

## 9. Follow-up A/B/C 3-block alignment check

This follow-up check was captured after the transient port 8003 degraded response. It confirms that ports 8001, 8002 and 8003 remained aligned while the chain advanced by at least 3 blocks.

Generated at: 2026-06-18 22:58:29 UTC

Target: prove that ports 8001, 8002 and 8003 remain aligned while the chain advances by at least 3 blocks.

```text
CHECK 1 2026-06-18 22:58:29 UTC RESULT=ALIGNED_OK height=41816 finalized=41815 hash=0944ee6bd82bf51c finalized_hash=a691bef74f88b431
  port=8001 status=ok height=41816 finalized=41815 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8002 status=ok height=41816 finalized=41815 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8003 status=ok height=41816 finalized=41815 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
POLL 2026-06-18 22:58:34 UTC RESULT=NOT_READY_OR_NOT_ALIGNED
  port=8001 status=ok height=41817 finalized=41816
  port=8002 status=ok height=41817 finalized=41816
  port=8003 status=ok height=41817 finalized=41816
CHECK 2 2026-06-18 22:58:39 UTC RESULT=ALIGNED_OK height=41817 finalized=41816 hash=f97929e033027b39 finalized_hash=0944ee6bd82bf51c
  port=8001 status=ok height=41817 finalized=41816 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8002 status=ok height=41817 finalized=41816 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8003 status=ok height=41817 finalized=41816 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
POLL 2026-06-18 22:59:04 UTC RESULT=NOT_READY_OR_NOT_ALIGNED
  port=8001 status=ok height=41818 finalized=41817
  port=8002 status=ok height=41818 finalized=41817
  port=8003 status=ok height=41818 finalized=41817
CHECK 3 2026-06-18 22:59:09 UTC RESULT=ALIGNED_OK height=41818 finalized=41817 hash=c251d92f405f48e5 finalized_hash=f97929e033027b39
  port=8001 status=ok height=41818 finalized=41817 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8002 status=ok height=41818 finalized=41817 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8003 status=ok height=41818 finalized=41817 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
POLL 2026-06-18 22:59:34 UTC RESULT=NOT_READY_OR_NOT_ALIGNED
  port=8001 status=ok height=41819 finalized=41818
  port=8002 status=ok height=41819 finalized=41818
  port=8003 status=ok height=41819 finalized=41818
CHECK 4 2026-06-18 22:59:39 UTC RESULT=ALIGNED_OK height=41819 finalized=41818 hash=0381679237cfd936 finalized_hash=c251d92f405f48e5
  port=8001 status=ok height=41819 finalized=41818 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8002 status=ok height=41819 finalized=41818 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True
  port=8003 status=ok height=41819 finalized=41818 runtime_bootstrap_complete=True runtime_sync_caught_up=True consensus_ready=True operational_runtime_quorum_ready=True p2p_ready_for_mining=True

FINAL_RESULT=PASS baseline_height=41816 final_height=41819 advanced_by=3
```

## What this proves

This evidence shows that a NewGen L1 node can recover from a clean local runtime state while preserving identity/config, prioritize snapshot bootstrap for a large peer gap, restore snapshot-backed state without a full replay from genesis, complete post-snapshot catchup, reach SteadyState, and rejoin the live validator/follower set with matching height, finalized state, and block hash.

## What this does not claim

This is not a public mainnet launch claim.

This is runtime evidence from the current NewGen test infrastructure.

It does not claim open validator onboarding or third-party permissionless operation.
