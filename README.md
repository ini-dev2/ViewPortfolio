# ViewPortfolio

- [[#Tools And Utilities]]
- [[#Plugins]]
- [[#Effects]]




## Tools And Utilities
## WebRTCWrapper
A lightweight wrapper over **Unity.WebRTC** with a Fluent API, UniTask support, and pluggable signaling. Send and receive video/audio tracks, handle ICE/SDP, and bring a peer-to-peer connection up in a few chained calls.
**Highlights**
- Fluent `Create().WithConfig(...).WithSignaling(...).WithMedia(...).Finish()`
- `IMedia` / `MediaCreator` for `VideoStreamTrack` and `AudioStreamTrack`
- Abstract `ISignaling` for WebSocket, HTTP, SignalR
- Optional Newtonsoft.Json attributes via the `Newtonsoft` define
**Links**
- Repository: [`https://github.com/ini-dev2/WebRTCWrapper`](https://github.com/ini-dev2/WebRTCWrapper)
- Documentation: [README →](https://github.com/ini-dev2/WebRTCWrapper#readme)
---
## UniStateMachine
A graph-based, data-driven state machine for Unity. Build state graphs visually with **Unity GraphToolkit** and import them as `ScriptableObject` assets — no boilerplate code required.
**Highlights**
- Visual graph editor with `StateMachineGraph`, `StartNode`, `StateNode<TStateId>`
- Custom `GraphRuntimeImporter` converts graphs into `StringKeyStateMachine` assets
- Generic `StateMachine<T>` core with `IState<T>` (enter/exit events)
- Editor validation for duplicate IDs, unreachable nodes, dangling references
**Links**
- Repository: [`https://github.com/ini-dev2/UniStateMachine`](https://github.com/ini-dev2/UniStateMachine)
- Documentation: [README →](https://github.com/ini-dev2/UniStateMachine#readme)
---
## RestBuilder
A lightweight, allocation-friendly REST client for Unity built on **UnityWebRequest** + **UniTask**. Fluent request builder, typed `Result<T>`, cancellation, retries with backoff, JSON serialization, interceptors, and byte/file downloads with progress.
**Highlights**
- `client.Request("/users/{id}").Path("id", 42).GetAsync<User>()`
- `Result<T>` with `IsSuccess`, `StatusCode`, `Error`, `ErrorBody`, `Data`
- Retries only for retryable statuses (0, 408, 429, 5xx) with backoff
- `DownloadAsync` / `DownloadToFileAsync` with atomic `.part` → `File.Move`
- `IRestInterceptor` and `IRestLogger` extension points
- `EndPointsConfig` `ScriptableObject` for named endpoints
**Links**
- Repository: [`https://github.com/ini-dev2/RestBuilder`](https://github.com/ini-dev2/RestBuilder)
- Documentation: [README →](https://github.com/ini-dev2/RestBuilder#readme)
---
## SqlCipherWrapper
A thread-safe, asynchronous wrapper around **SQLCipher** for Unity. All database operations run on a dedicated background thread, serialized through a bounded queue and exposed as `UniTask` methods.
**Highlights**
- Encrypted at rest via SQLCipher (`SqlCipher4Unity3D`)
- `DbWorker` owns the `SQLiteConnection` — it never leaves the worker thread
- `DbService` / `IDbService` with generic CRUD, transactions, raw SQL
- `DbServiceFactory.CreateAsync(...)` for async bootstrap
- `IDbLogger`, `IDbConnectionFactory`, `DbWorkerOptions` for customization
- `DbTestRunner` MonoBehaviour with 8 scenarios for Play Mode testing
**Links**
- Repository: [`https://github.com/ini-dev2/SqlCipherWrapper`](https://github.com/ini-dev2/SqlCipherWrapper)
- Documentation: [README →](https://github.com/ini-dev2/SqlCipherWrapper#readme)
---
## Tickable
A lightweight, allocation-conscious tick system for Unity. Register any `IUpdateTick` into one of three groups — **every frame**, **fixed tick rate**, or **custom interval** — and drive them from a single `PlayerLoop` hook.
**Highlights**
- Three tick modes: `NONE` (frame), `ON_TICKRATE` (fixed rate), `ON_SECONDS` (custom interval)
- Single PlayerLoop hook — no `MonoBehaviour.Update()` sprawl
- Exception isolation — one bad tick does not stop the loop
- `HashSet` registration + cached interval groups
- `PlayHook` / `StopHook` for pausing without unregistering
**Links**
- Repository: [`https://github.com/ini-dev2/Tickable`](https://github.com/ini-dev2/Tickable)
- Documentation: [README →](https://github.com/ini-dev2/Tickable#readme)
---
## TourverseToolkit
An editor toolkit for building, packing, and uploading Unity **tours** (scene + Addressables + DLL bundles) to a remote backend.
**Highlights**
- Settings window for `Authorization`, `Project Settings`, `Validation`
- `ScenarioDataBuilder` orchestrates DLL compilation, link.xml, Addressables
- IL-based `LinkXmlGenerator` using Mono.Cecil
- Addressables automation: groups, labels, per-target build/load paths
- `PackerService` (7-Zip) + `UploadService` with streaming progress
- `RenameNamespaceInAssemblyService` for bulk namespace edits
- `TT_CIRunner.Build()` for batchmode CI builds
- `LayerCollisionConfigEditor` — custom 32×32 collision matrix inspector
**Links**
- Repository: [`https://github.com/ini-dev2/TourverseToolkit`](https://github.com/ini-dev2/TourverseToolkit)
- Documentation: [README →](https://github.com/ini-dev2/TourverseToolkit#readme)
---






## Plugins







## Effects
