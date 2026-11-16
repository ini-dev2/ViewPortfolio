# ViewPortfolio
- [Game Projects](#game-projects)
- [Tools And Utilities](#tools-and-utilities)
- [Plugins](#plugins)
- [Effects](#effects)


# Game Projects





# Tools And Utilities
## WebRTCWrapper
A lightweight wrapper over **Unity.WebRTC** with a Fluent API, UniTask support, and pluggable signaling. Send and receive video/audio tracks, handle ICE/SDP, and bring a peer-to-peer connection up in a few chained calls.
**Highlights**
- Fluent `Create().WithConfig(...).WithSignaling(...).WithMedia(...).Finish()`
- `IMedia` / `MediaCreator` for `VideoStreamTrack` and `AudioStreamTrack`
- Abstract `ISignaling` for WebSocket, HTTP, SignalR
- Optional Newtonsoft.Json attributes via the `Newtonsoft` define
**Links**
- Repository: [`REPO`](https://github.com/ini-dev2/WebRTCWrapper)
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
- Repository: [REPO](https://github.com/ini-dev2/Tools/tree/main/Assets/Plugins/_StateMachine)
- Documentation: [README →](https://github.com/ini-dev2/Tools/blob/main/Assets/Plugins/_StateMachine/Documentation.md)
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
- Repository: [REPO](https://github.com/ini-dev2/Tools/tree/main/Assets/Plugins/_RestBuilder)
- Documentation: [README →](https://github.com/ini-dev2/Tools/blob/main/Assets/Plugins/_RestBuilder/DOCS.md)
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
- Repository: [`REPO`](https://github.com/ini-dev2/Tools/tree/main/Assets/Plugins/_SqlCipherWrapper)
- Documentation: [README →](https://github.com/ini-dev2/Tools/blob/main/Assets/Plugins/_SqlCipherWrapper/DOCS.md)
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
- Repository: [`REPO`](https://github.com/ini-dev2/Tools/tree/main/Assets/Plugins/_Tickable)
- Documentation: [README →](https://github.com/ini-dev2/Tools/blob/main/Assets/Plugins/_Tickable/DOCS.md)
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
- Repository: [`REPO`](https://github.com/ini-dev2/TourverseToolkit)
- Documentation: [README →](https://github.com/ini-dev2/TourverseToolkit#readme)
---






# Plugins
## AndroidApkInstallerPlugin4Unity

A lightweight Android plugin for Unity that installs APK files programmatically on Android devices, including Android 8.0+ where the **"Install unknown apps"** permission is required. Handles permission requests, generates content URIs via `FileProvider`, and safely launches the installer intent.

**Highlights**

- Supports Android 6.0 (API 23) and above
- Automatically requests `REQUEST_INSTALL_PACKAGES` on Android 8.0+
- Uses `FileProvider` to avoid `FileUriExposedException` on Android 7.0+
- Clean C# API (`installApk(path)`) callable from any `MonoBehaviour`
- No external dependencies
- Ideal for self-updating apps, AAB splits, and expansion files

**Links**

- Repository: [`REPO`](https://github.com/ini-dev2/AndroidApkInstallerPlugin4Unity)
- Sample project: [UnityAndroidApkInstallerPluginSample](https://github.com/ini-dev2/UnityAndroidApkInstallerPluginSample)
- Documentation: [README →](https://github.com/ini-dev2/AndroidApkInstallerPlugin4Unity#readme)

---






# Effects

## Vertical World Dissolve Shader URP
https://www.youtube.com/watch?v=TJtncmxietY
