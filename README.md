CodeContracts.MSBuild
=====================

Standalone MSBuild integration for [Microsoft CodeContracts](https://github.com/microsoft/codecontracts) (by Microsoft Research).

## Installation

Simply add `CodeContracts.MSBuild` nuget to projects that use Code Contracts.

From package manager:

```
Install-Package CodeContracts.MSBuild
```

From .Net CLI:

```
dotnet add package CodeContracts.MSBuild
```

## Settings

### `DontOverrideCodeContractsInstallDir`, `CodeContractsInstallDir`

By default `CodeContracts.MSBuild` uses CodeContracts version that is bundled with this package.

However, if you want to use custom CodeContracts installation,
you can define the following MSBuild properties in your project file:

```xml
<PropertyGroup>
  <DontOverrideCodeContractsInstallDir>true<DontOverrideCodeContractsInstallDir>
  <CodeContractsInstallDir>your_custom_codecontracts_install_dir\</CodeContractsInstallDir>
</PropertyGroup>
```

### `CodeContracts*`

`CodeContracts.MSBuild` defines a bunch of default properties that are used by Microsoft CodeContracts.
Please refer to CodeContracts for meaning of these options.

| Property | Default value | Description |
|----------|---------------|-------------|
| **Runtime checking** |
| `CodeContractsEnableRuntimeChecking` | `False` | Runtime checking. If `False`, whole section is irrelevant. |
| `CodeContractsAssemblyMode` | `1` | Assembly mode, `1` = standard, `2` = advanced. |
| `CodeContractsRuntimeCheckingLevel` | `Full` | Level: `Full`, `Pre and Post`, `Preconditions`, `ReleaseRequires`, `None` |
| `CodeContractsRuntimeOnlyPublicSurface` | `False` | Only public surface contracts |
| `CodeContractsRuntimeThrowOnFailure` | `False` | Assert on contract failure |
| `CodeContractsRuntimeCallSiteRequires` | `False` | Call-site requires checking | `CodeContractsRuntimeSkipQuantifiers` | `False` | Skip quantifiers |
| `CodeContractsCustomRewriterAssembly` | *empty* | Custom rewriter methods / Assembly |
| `CodeContractsCustomRewriterClass` | *empty* | Custom rewriter methods / Class |
| **Static checking** |
| `CodeContractsRunCodeAnalysis` | `True` | Static checking. If `False`, whole section is irrelevant. |
| `CodeContractsNonNullObligations` | `True` | Check non-null |
| `CodeContractsEnumObligations` | `True` | Check enum values |
| `CodeContractsRedundantAssumptions` | `True` | Check redundant assume |
| `CodeContractsSuggestAssumptions` | `False` | Show entry assumptions |
| `CodeContractsSuggestRequires` | `False` | Suggest requires |
| `CodeContractsAssertsToContractsCheckBox` | `True` | Suggest asserts to contracts |
| `CodeContractsInferRequires` | `True` | Infer requires |
| `CodeContractsInferEnsures` | `False` | Infer ensures |
| `CodeContractsArithmeticObligations` | `True` | Check arithmetic |
| `CodeContractsMissingPublicRequiresAsWarnings` | `True` | Check missing public requires |
| `CodeContractsRedundantTests` | `True` | Check redundant conditionals |
| `CodeContractsSuggestAssumptionsForCallees` | `False`| Show external assumptions |
| `CodeContractsSuggestReadonly` | `True`| Suggest readonly fields |
| `CodeContractsNecessaryEnsures` | `True` | Suggest necessary ensures |
| `CodeContractsInferObjectInvariants` | `False` | Infer invariants for readonly |
| `CodeContractsInferEnsuresAutoProperties` | `True` | Infer ensures for autoproperties |
| `CodeContractsFailBuildOnWarnings` | `False` | Fail build on warnings |
| `CodeContractsBoundsObligations` | `True` | Check array bounds |
| `CodeContractsMissingPublicEnsuresAsWarnings` | `False` | Check missing public ensures |
| `CodeContractsSuggestObjectInvariants` | `False` | Suggest object invariants |
| **Misc**
| `CodeContractsCacheAnalysisResults` | `True` | Cache results |
| `CodeContractsSQLServerOption` | *empty* | SQL Server |
| `CodeContractsSkipAnalysisIfCannotConnectToCache` | `False` | Skip the analysis if cannot connect to cache |
| `CodeContractsAnalysisWarningLevel` | `0` | Warning level: `0`, `1, `2`, `3` |
| `CodeContractsBeingOptimisticOnExternal` | `True` | Be optimistic on external API |
| `CodeContractsUseBaseLine` | `False` | Baseline |
| `CodeContractsBaseLineFile`| *empty* | Baseline file |
| `CodeContractsReferenceAssembly` | `Build` | Contract reference assembly |
| `CodeContractsEmitXMLDocs` | `False` | Emit contracts into XML doc file |
| **Advanced options** |
| `CodeContractsLibPaths` | *empty* | Extra contract library paths |
| `CodeContractsExtraRewriteOptions` | *empty* | Extra runtime checker options |
| `CodeContractsExtraAnalysisOptions` | *empty* | Extra static checker options |
