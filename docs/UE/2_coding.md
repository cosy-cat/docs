---
title: Coding
tags:
- unreal-engine
---

## VsCode build 

- run build task: ${Project}Editor Win64 Development Build

## Tick

- called every frame `deltaTime` parameter: to be used to make operations "frame rate independent" (by * speed of movement by deltaTime for instance)

## Log

[docs](https://dev.epicgames.com/documentation/en-us/unreal-engine/logging-in-unreal-engine)

```cpp
UE_LOG(LogTemp, Level, TEXT("message"));
```

## Adding CPP class

💡 1st time :

- Use default location
- close editor UE
- in vscode, terminal/run/task  `*Win64 Development Build`

- reopen UE editor, now the C++ project folder with the cpp files will appear in the content drawer

Now and next times :

- in tools menu regenerate project files (avoid sqwiggles in vscode)

## CPP particularities

### CONST Method

```cpp
bool Namespace::AMethod() const

// ℹ️ this method cannot modify the state of the object, or it results in a compile error 
// For instance, if using in the method:
// SetActorLocation = ❌
// GetActorLocation = ✅
```

## FRotator

💡 tips for continuous rotation:

```cpp
AddActorLocalRotation(RotationVelocity * DeltaTime);
```
