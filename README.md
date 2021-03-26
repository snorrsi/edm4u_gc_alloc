# Example project for EDM4U GC Allocation.

[See EDM4U issue #428](https://github.com/googlesamples/unity-jar-resolver/issues/428)

This is sample project based on 3D Template from Unity 2020.3.1f
Only change made in this in Packages/manifest.json where EDM4U has been added as a package.

## How to replicate the issue.

1. Opening the project in Unity 2020.3.1f
2. Open the Assets/Scene/SampleScene.unity
3. Press Play
4. Start the Unity Profiler under Window / Analysis / Profiler (or Profiler standalone).
5. Selecting Editor in the dropdown menu to debug the editor instead of the Playmode to get the Editor GC Collection information.
6. Enable Call Stacks / GC Alloc on the top right side of the Profiler
7. Press Record button in Profiler to start recording GC Alloc
8. Wait for few frames
9. Press Record butto in Profiler to stop recording GC Alloc

## Reading the data (after following above steps)
1. In CPU Usage. Select some frame in the under and check GC Alloc origination.
2. Under Raw Hierarchy, Main Thread search for "ExecuteAll"
3. Select the ExecuteAll line, press x to view the contents there under.
4. Check the origination of GC Alloc by pressing any GC.Alloc line
5. Notice way to many of the belong to EDM4U
