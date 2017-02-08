---
category: "Android"
---


Espresso custom ViewAssertion to check RecyclerView's number of items.

```java
public class RecyclerViewNoItemsAssertion implements ViewAssertion {

    private final int expectedNoItems;

    public RecyclerViewNoItemsAssertion(int expectedNoItems) {
        this.expectedNoItems = expectedNoItems;
    }

    @Override
    public void check(View view, NoMatchingViewException noViewFoundException) {
        if (noViewFoundException != null) {
            throw noViewFoundException;
        }

        RecyclerView recyclerView = (RecyclerView) view;
        RecyclerView.Adapter adapter = recyclerView.getAdapter();
        assertThat(adapter.getItemCount(), is(expectedNoItems));
    }

}
```

Usage
```java
onView(withId(R.id.recycler_view_categories)).check(new RecyclerViewNoItemsAssertion(5));
```
