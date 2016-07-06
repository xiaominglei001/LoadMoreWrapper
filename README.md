# RecyclerAdapter

Without changes to the original adater of recyclerView, make recyclerView supports load more and customize the footer view

在不改动RecyclerView原有adapter的情况下，使其拥有加载更多功能和自定义底部视图。

## Installation

add the dependency to your build.gradle:
```
    compile 'com.github.nukc.recycleradapter:recycleradapter:0.3.5'
```

## Usage

since v0.3.0, you can :

```java
    //the adapter is the original (这个adapter是原有的, 不改动它)
    RecyclerWrapper.with(adapter)
        .setFooterView(...)
        .setListener(new RecyclerAdapter.OnLoadMoreListener() {
             @Override
             public void onLoadMore(RecyclerAdapter.Enabled enabled) {
                 //do something
                 //you can enabled.setLoadMoreEnabled(false) when do not need load more
             })
        .into(recyclerView);
```

general :

```java
    RecyclerAdapter recyclerAdapter = new RecyclerAdapter(adapter);
    recyclerView.setAdapter(recyclerAdapter);

    //set load more listener
    recyclerAdapter.setLoadMoreListener(new RecyclerAdapter.OnLoadMoreListener() {
        @Override
        public void onLoadMore(RecyclerAdapter.Enabled enabled) {
            //do something
        }
    });

    //设置是否启用加载更多
    setLoadMoreEnabled(boolean enabled)

    //customize the footer view
    public RecyclerAdapter(@NonNull RecyclerView.Adapter adapter, View footerView)

    public RecyclerAdapter(@NonNull RecyclerView.Adapter adapter, @LayoutRes int resId)

    setFooterView(View footerView)

    setFooterView(@LayoutRes int resId)
```

欢迎大家issues, star, fork, PR.

在纠结要不要加下拉刷新...
to be continued...

## License

    Copyright 2016, nukc

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.