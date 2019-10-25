## Nicole Beller: GAM-495 Capstone 

### Refined Artifact #2 - *Paintball_Fiasco*

### **Tools Used**
 - Visual Studio 2015
 - Visual Studio 2017
 - Unreal Engine 4.18
 - Various YouTube Tutorials
 
 
 
### **Inclusion**

When it comes to game programming, this artifact had to be included in my ePortfolio. This game was created in April of 2019 for my GAM-415 Graphics Game Engine course and it was the most intense class I have taken. Nearly every aspect of this game was created from scratch through the use of programming (C++), shaders, and plugins and a lot of blood, sweat, tears, and restarts. What I was able to accomplish in this game was beyond all of my expectations and even though the game is small, I think it has a lot of potential to grow into something great.

Quick code snippet of a simple cube:


```markdown
 Cube.h
…
protected:
      // Needed to display a visual component
      UPROPERTY(VisibleAnywhere)
             USceneComponent* ThisScene;
 
      // Displays the cube mesh
      UPROPERTY(VisibleAnywhere)
             UProceduralMeshComponent* ThisMesh;
 
      // Makes the cube visible when spawned/dragged into the world
      virtual void PostActorCreated() override;
 
      // Makes the cube visible whenever the level loads
      virtual void PostLoad() override;
 
      // Declares the cube's mesh form
      void GenerateMesh();
…

Cube.cpp
 …
// Updates the material within the game world via variables
void ACube::GenerateMesh()
{
      Vertices.Reset();
      Triangles.Reset();
      Normals.Reset();
      Tangents.Reset();
      UVs.Reset();
      Colors.Reset();
 
      // Keeps track of the triangles (every shape is made up of triangles)
      int32 TriangleIndexCount = 0;
      FVector DefinedShape[8];
      FProcMeshTangent TangentSetup;
 
      // Defines the shape
      DefinedShape[0] = FVector(CubeRadius.X, CubeRadius.Y, CubeRadius.Z); // Forward Top Right
      DefinedShape[1] = FVector(CubeRadius.X, CubeRadius.Y, -CubeRadius.Z); // Forward Bottom Right
      DefinedShape[2] = FVector(CubeRadius.X, -CubeRadius.Y, CubeRadius.Z); // Forward Top Left
      DefinedShape[3] = FVector(CubeRadius.X, -CubeRadius.Y, -CubeRadius.Z); // Forward Bottom Left
      DefinedShape[4] = FVector(-CubeRadius.X, -CubeRadius.Y, CubeRadius.Z); // Forward Top Right
      DefinedShape[5] = FVector(-CubeRadius.X, -CubeRadius.Y, -CubeRadius.Z); // Forward Bottom Right
      DefinedShape[6] = FVector(-CubeRadius.X, CubeRadius.Y, CubeRadius.Z); // Forward Top Left
      DefinedShape[7] = FVector(-CubeRadius.X, CubeRadius.Y, -CubeRadius.Z); // Forward Bottom Left
 
      // Passes the defined shape to generate the mesh
      // Front
      TangentSetup = FProcMeshTangent(0.f, 1.f, 0.f);
      AddQuadMesh(DefinedShape[0], DefinedShape[1], DefinedShape[2], DefinedShape[3], TriangleIndexCount, TangentSetup);
      // Left
      TangentSetup = FProcMeshTangent(1.f, 0.f, 0.f);
      AddQuadMesh(DefinedShape[2], DefinedShape[3], DefinedShape[4], DefinedShape[5], TriangleIndexCount, TangentSetup);
      // Back
      TangentSetup = FProcMeshTangent(0.f, -1.f, 0.f);
      AddQuadMesh(DefinedShape[4], DefinedShape[5], DefinedShape[6], DefinedShape[7], TriangleIndexCount, TangentSetup);
      // Right
      TangentSetup = FProcMeshTangent(-1.f, 0.f, 0.f);
      AddQuadMesh(DefinedShape[6], DefinedShape[7], DefinedShape[0], DefinedShape[1], TriangleIndexCount, TangentSetup);
      // Top
      TangentSetup = FProcMeshTangent(0.f, 1.f, 0.f);
      AddQuadMesh(DefinedShape[6], DefinedShape[0], DefinedShape[4], DefinedShape[2], TriangleIndexCount, TangentSetup);
      // Bottom
      TangentSetup = FProcMeshTangent(0.f, -1.f, 0.f);
      AddQuadMesh(DefinedShape[1], DefinedShape[7], DefinedShape[3], DefinedShape[5], TriangleIndexCount, TangentSetup);
 
      // Creates the shape
      ThisMesh->CreateMeshSection_LinearColor(0, Vertices, Triangles, Normals, UVs, Colors, Tangents, true);
}
…

```

This game shows my interest in programming; instead of just clicking and dragging cubes or spheres into my game, I learned how to program them and could manipulate some of the edges to create unique shapes.  I also learned to manipulate a shader so that when a player enters a specific object’s box collision, the color of the object will change. For a paintball game, showing other players your location can be a blessing in disguise or an absolute nightmare.

![Original](https://github.com/NicBee/NicBee.github.io/blob/master/Paintball_Fiasco_2.jpg?raw=true "Original")

![Altered](https://github.com/NicBee/NicBee.github.io/blob/master/Paintball_Fiasco_3.jpg?raw=true "Altered")

A quick code snippet of my color-changing steps:

```markdown
Steps2.h
…
private:
      // Defines the different points of the mesh, tells UE how to apply static meshes to steps
      TArray<FVector>Vertices;
 
      // Buffer (address) points to vertices, saves memory
      TArray<int32>Triangles;
 
      // Tells UE which way the surface of the steps are facing
      TArray<FVector>Normals;
 
      // Perpendicular angle to the normal (90 degrees)
      TArray<FRuntimeMeshTangent>Tangents;
 
      // Lets 3D renderer know how to apply the meshes and what kind of pattern the texture should have
      TArray<FVector2D>UVs;
 
      // Supposed to change the vertices colors
      TArray<FColor>Colors;
 
      // Triangle shape
      void AddTriangleMesh(FVector A, FVector B, FVector C, int32& TriIndex, FRuntimeMeshTangent tangent);
 
      // Activates when the player walks over the box collision of the mesh
      virtual void NotifyActorBeginOverlap(AActor* OtherActor);
 
      // Ends overlap (material reverts back to original)
      virtual void NotifyActorEndOverlap(AActor* OtherActor);
…
 
Steps2.cpp
…
// Sets default values
ASteps2::ASteps2()
{
      // Makes the scene component a root component
      ThisScene = CreateDefaultSubobject<USceneComponent>(TEXT("Root"));
      RootComponent = ThisScene;
 
      // Attaches the RuntimeMeshComponent to the new root component
      ThisMesh = CreateDefaultSubobject<URuntimeMeshComponent>(TEXT("GeneratedMesh"));
      ThisMesh->SetupAttachment(RootComponent);
 
      // Adds the box collision to change the material
      ThisCollision = CreateDefaultSubobject<UBoxComponent>(TEXT("Trigger"));
      ThisCollision->InitBoxExtent(StepRadius * 1.1f);
      ThisCollision->SetupAttachment(RootComponent);
      ThisCollision->SetCollisionEnabled(ECollisionEnabled::QueryOnly);
      ThisCollision->SetCollisionResponseToAllChannels(ECR_Ignore);
      ThisCollision->SetCollisionResponseToChannel(ECC_Pawn, ECR_Overlap);
 
      // Sets the material at creation, runtime can change it
      static ConstructorHelpers::FObjectFinder<UMaterial> MaterialAsset(TEXT("/Game/Materials/m_Red.m_Red"));
      if (MaterialAsset.Succeeded())
      {
             MaterialA = MaterialAsset.Object;
      }
 
      // Sets the material at creation, runtime can change it
      static ConstructorHelpers::FObjectFinder<UMaterial> MaterialAssetB(TEXT("/Game/Materials/m_Blue.m_Blue"));
      if (MaterialAssetB.Succeeded())
      {
             MaterialB = MaterialAssetB.Object;
      }
 
}
…


```

Another aspect of this game that makes it appealing and stands out is how colorful it is. The level design itself is rather simple, with blacks, whites, and some neon colors, but the paintballs are programmed to shoot out random colors, adding even more colorful fun to the game. 

![Colors](https://github.com/NicBee/NicBee.github.io/blob/master/Paintball_Fiasco_1.jpg?raw=true "Colors")

### **Skills Learned**
  - Display 3D objects in game development environments by employing graphics application program interfaces
  - Apply texture and material to meshes adding 2D images to 3D models
  - Apply shaders to geometric objects in game development environments by employing graphics application program interfaces
  - Relate graphics application program interfaces to the output of graphic game engines for making informed game project decisions
  - Differentiate among graphics application program interfaces in examining current trends in game engine architecture
  
### **Highlighted Skills**
  - Game Engine Mastery: showcases that I can use programming along with blueprints, shaders, and plugins within the Unreal Engine.  I consider it mastery becasue there aren't a lot of tutorials for C++/VS online for UE4, which means it can be considered hard to learn and understand.
  - 3D Graphics: showcases my basic shapes.  Anyone can click and drag a square or sphere from the side, but it takes skill and dedication to learn how to script a square or sphere from scratch.
  - Programming: showcases my interest and talent in coding.  Since most of the objects and actors were created from scratch by using C++ and Visual Studio, the game shows that I have a deep understanding of how C++ works with the Unreal Engine.
  
### **Revised Components**
- Game Engine Mastery
- 3D Graphics
- Plugins & Shaders
  
### **Reflection**


### Return

Click here to return to the main page: [Home](/index.md)
