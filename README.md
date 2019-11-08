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

```
Copyright 2019 Mohammad Sianaki.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
