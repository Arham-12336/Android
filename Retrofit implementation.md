# Retrofit Implementation:
Retrofit is a popular REST client library for Android and Java that
makes it easy to consume REST APIs in an app. It provides a
simple, annotation-based API for performing HTTP requests and
handling the responses.

## Step 01:
Add the following dependencies to your build.gradle file:

```kotlin

implementation 'com.squareup.retrofit2:retrofit:2.9.0'
implementation 'com.squareup.retrofit2:converter-gson:2.9.0'

```

## Step 02:
Create an interface to define the REST API endpoints:

```kotlin

interface ApiService {
    @GET("users/{user}/repos")
    fun getRepos(@Path("user") user: String): Call<List<Repo>>
}

```

## Step 03:
Create a Retrofit instance and configure it to use the Gson converter:

```kotlin

val retrofit = Retrofit.Builder()
    .baseUrl("https://api.github.com/")
    .addConverterFactory(GsonConverterFactory.create())
    .build()

```
## Step 04:
Create a ApiService instance and call the API endpoint:

```kotlin

val api = retrofit.create(ApiService::class.java)
val call = api.getRepos("octocat")
call.enqueue(object : Callback<List<Repo>> {
    override fun onResponse(call: Call<List<Repo>>, response: Response<List<Repo>>) {
        val repos = response.body()
        // Handle the response
    }

    override fun onFailure(call: Call<List<Repo>>, t: Throwable) {
        // Handle the failure
    }
})


```


That's it! With these steps, you should be able to implement Retrofit in your Android application using Kotlin. You can refer to the Retrofit documentation for more information on how to use it in your projects.