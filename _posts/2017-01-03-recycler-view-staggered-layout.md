How to customize the RecyclerView layout, make it has different number of items on each row.

<img src="https://raw.githubusercontent.com/trinhlbk1991/til/master/android/Screen%20Shot%202017-01-03%20at%207.08.29%20PM.png" width="350"/>

```
GridLayoutManager layoutManager = new GridLayoutManager(activity, MAX_SPAN);
layoutManager.setSpanSizeLookup(new GridLayoutManager.SpanSizeLookup() {
    @Override
    public int getSpanSize(int position) {
        return presenter.getSpanSize(position);
    }
});
binding.recyclerView.setLayoutManager(layoutManager);
```
