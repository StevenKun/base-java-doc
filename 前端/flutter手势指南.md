- Tap

  - `onTapDown` - 一个可能产生点击事件的指针触摸到屏幕的特定位置。

    `onTapDown` - A pointer that might cause a tap has contacted the screen at a particular location.

  - `onTapUp` - 一个产生了点击事件的指针停止触摸屏幕的特定位置。

    `onTapUp` - A pointer that triggers a tap has stopped contacting the screen at a particular location.

  - `onTap` - 一个点击事件已经发生。

  - `onTapCancel` - 之前触发了 `onTapDown` 事件的指针不会产生点击事件。

- Double tap

  - `onDoubleTap` - 用户在屏幕同一位置连续快速地点击两次。

- Long press

  - `onLongPress` - 指针在屏幕的同一位置保持了一段较长时间的触摸状态。

- Vertical drag

  - `onVerticalDragStart` - 指针已经触摸屏幕并可能开始垂直移动。
  - `onVerticalDragUpdate` - 触摸屏幕的指针在垂直方向移动了更多的距离。
  - `onVerticalDragEnd` - 之前和屏幕接触并垂直移动的指针不再继续和屏幕接触，并且在和屏幕停止接触的时候以一定的速度移动。

- Horizontal drag

  - `onHorizontalDragStart` - 指针已经触摸屏幕并可能开始水平移动。
  - `onHorizontalDragUpdate` - 触摸屏幕的指针在水平方向移动了更多的距离。
  - `onHorizontalDragEnd` - 之前和屏幕接触并水平移动的指针不再继续和屏幕接触，并且在和屏幕停止接触的时候以一定的速度移动。