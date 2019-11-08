# Retrofit2-Flow-Call-Adapter
A Retrofit 2 `CallAdapter.Factory` for [Kotlin Flows](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines.flow/-flow/)

## Usage
Add `FlowCallAdapterFactory` as a `CallAdapter` when building your retrofit instance:

```Kotlin
     val retrofit = Retrofit.Builder()
    .baseUrl("https://example.com/")
    .addCallAdapterFactory(FlowCallAdapterFactory.create())
    .build()
```

Your service methods can now use `Flow` as their return type.

```Kotlin
interface WebService {
  @GET("/user")
  fun getUser(): Flow<UserDto>

  // or

  @GET("/user")
  fun getUser(): Flow<Response<UserDto>>
}
````

## Downlaod
**Step 1.** Add the JitPack repository to your build file:

```Gradle
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

**Step 2.** Add the dependency:

```Gradle
dependencies {
	      implementation 'com.github.MohammadSianaki:Retrofit2-Flow-Call-Adapter:latest-version'
}
```

## Licence
