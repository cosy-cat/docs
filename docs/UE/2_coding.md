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

## git lfs

```sh
# Once only
sudo apt-get install git-lfs
git lfs install

git lfs track "*.uasset"
git lfs track "*.umap"
git lfs track "*.png"
git lfs track "*.jpg"
git lfs track "*.tga"
git lfs track "*.wav"
git lfs track "*.mp3"
git lfs track "*.fbx"

```

- add file at root of project `.gitattributes`:

```txt
# Unreal Engine binary assets
*.uasset filter=lfs diff=lfs merge=lfs -text
*.umap   filter=lfs diff=lfs merge=lfs -text

# Common large binary types
*.png    filter=lfs diff=lfs merge=lfs -text
*.jpg    filter=lfs diff=lfs merge=lfs -text
*.tga    filter=lfs diff=lfs merge=lfs -text
*.wav    filter=lfs diff=lfs merge=lfs -text
*.mp3    filter=lfs diff=lfs merge=lfs -text
*.mov    filter=lfs diff=lfs merge=lfs -text
*.mp4    filter=lfs diff=lfs merge=lfs -text
*.fbx    filter=lfs diff=lfs merge=lfs -text

# Optional (if using Megascans/Metahuman, add more formats like EXR, TIFF, etc.)
```

```sh
# for each project
git init
git add .gitattributes
git add .
git commit -m "Initial Unreal project with Git LFS"
```

- check:

```sh
git lfs ls-files
```

> You should see .uasset, .umap, and other large binaries listed.

