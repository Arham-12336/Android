# Recycler View

RecyclerView is a flexible and efficient version of the ListView in Android. It's designed to handle large amounts of data efficiently and provides a smooth scrolling experience to the users. The main difference between ListView and RecyclerView is that RecyclerView is more efficient in terms of performance and memory usage.

A RecyclerView displays a list of items in a vertically scrolling list. Each item in the list is represented by a view holder object, which recycles the view objects as needed. This recycling process helps to improve the performance and reduce the memory usage of the RecyclerView. The RecyclerView also provides built-in support for animations and item decorations, making it easier to customize the look and feel of the list.

To use RecyclerView in your Android app, you need to define a custom adapter that inherits from RecyclerView.Adapter. The adapter is responsible for creating and binding the view holder objects, and it also defines the data that should be displayed in each item of the list.



## Difference between Listview and Recyclerview

ListView is the ancestor to RecyclerView. There were many things that ListView either didn't do, or didn't do well. If you were to gather the shortcomings of the ListView and solved the problem by abstracting the problems into different domains you'd end up with something like the recycler view. Here are the main problem points with ListViews:

- Didn't enforce View Reuse for same item types (look at one of the adapters that are used in a ListView, if you study the getView method you will see that nothing prevents a programmer from creating a new view for every row even if one is passed in via the convertView variable)

- Didn't prevent costly findViewById uses(Even if you were recycling views as noted above it was possible for devs to be calling findViewById to update the displayed contents of child views. The main purpose of the ViewHolder pattern in ListViews was to cache the findViewById calls. However this was only available if you knew about it as it wasn't part of the platform at all)

- Only supported Vertical Scrolling with Row displayed Views (Recycler view doesn't care about where views are placed and how they are moved, it's abstracted into a LayoutManager. A Recycler can therefore support the traditional ListView as shown above, as well as things like the GridView, but it isn't limited to that, it can do more, but you have to do the programming foot work to make it happen).

- Animations to added/removed was not a use case that was considered. It was completely up to you to figure out how go about this (compare the RecyclerView. Adapter classes notify* method offerings v. ListViews to get an idea).

In short RecyclerView is a more flexible take on the ListView, albeit more coding may need to be done on your part.


## Components of recyclerview

A RecyclerView in Android consists of several components:

- RecyclerView: The main component that displays the list of items.

- ViewHolder: A class that holds the references to the views that represent each item in the list. The ViewHolder objects are created and managed by the RecyclerView.Adapter.

- Adapter: A class that binds the data to the RecyclerView and creates the ViewHolder objects. The Adapter also defines how the data should be displayed in each item of the list.

- LayoutManager: A class that is responsible for laying out the items in the RecyclerView. There are several built-in LayoutManager classes, including LinearLayoutManager, GridLayoutManager, and StaggeredGridLayoutManager.

- ItemAnimator: A class that provides animations for changes in the RecyclerView. There are several built-in ItemAnimator classes, including DefaultItemAnimator, FadeInAnimator, and SlideInLeftAnimator.

- ItemDecoration: A class that provides visual decorations for the items in the RecyclerView. ItemDecorations can be used to add dividers, margins, and other visual elements to the list.

- These are the main components of a RecyclerView in Android. By combining these components, you can create a flexible and efficient list-based user interface in your Android app.

## Implement a Recycler view in Android:

A RecyclerView in Android consists of several components:

To implement a RecyclerView in Android, you need to perform the following steps:

Step 1: Add the RecyclerView library to your project's build.gradle file.

Step 2: Create a layout file for each item in the list. This layout file should define the views that represent the data for each item.

```kotlin

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <TextView
        android:id="@+id/text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</LinearLayout>

```



Step 3: Create a custom adapter class that extends the RecyclerView.Adapter class. In this class, you need to define the following methods:

```kotlin

class MyAdapter extends RecyclerView.Adapter<MyAdapter.MyViewHolder> {

    private List<String> data;

    public MyAdapter(List<String> data) {
        this.data = data;
    }

    @NonNull
    @Override
    public MyViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        View view = LayoutInflater.from(parent.getContext())
                .inflate(R.layout.item_layout, parent, false);
        return new MyViewHolder(view);
    }

    @Override
    public void onBindViewHolder(@NonNull MyViewHolder holder, int position) {
        holder.textView.setText(data.get(position));
    }

    @Override
    public int getItemCount() {
        return data.size();
    }
```

Step 4: Create a ViewHolder class

 onCreateViewHolder: Creates a new ViewHolder object and inflates the item layout file.

 ```kotlin

    class MyViewHolder extends RecyclerView.ViewHolder {

        TextView textView;

        public MyViewHolder(@NonNull View itemView) {
            super(itemView);
            textView = itemView.findViewById(R.id.text_view);
        }
    }
}
 ```


Step 5: In your activity or fragment, create an instance of the RecyclerView and set its layout manager and adapter.

```kotlin 

public class MainActivity extends AppCompatActivity {

    private RecyclerView recyclerView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        }
```

Set the data to be displayed in the RecyclerView by calling the adapter's notifyDataSetChanged method.


## Concepts of Data Classes, Adapters, Layout Managers and Item animators 

- Data Classes: Data classes are classes that represent the data that is displayed in a RecyclerView. The data is usually stored in a collection, such as a List, and can be of any type, such as strings, numbers, or custom objects.

- Adapters: Adapters are classes that bind the data to the RecyclerView. They are responsible for creating the ViewHolder objects, which hold the references to the views that represent each item in the list, and for binding the data to these views. The Adapter class also defines how the data should be displayed in each item of the list.

- Layout Managers: Layout Managers are classes that control the layout of the items in the RecyclerView. They determine the size and position of each item, as well as the scrolling behavior of the RecyclerView. There are several built-in LayoutManager classes, including LinearLayoutManager, GridLayoutManager, and StaggeredGridLayoutManager, that you can use to implement different types of lists.

- Item Animators: Item Animators are classes that provide animations for changes in the RecyclerView, such as when items are added, removed, or changed. There are several built-in ItemAnimator classes, including DefaultItemAnimator, FadeInAnimator, and SlideInLeftAnimator, that you can use to create different types of animations for your RecyclerView.