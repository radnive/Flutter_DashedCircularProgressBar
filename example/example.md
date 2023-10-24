# Basic examples
Here are some simple examples you can use to create this package:

### Example 1 - Simple progress bar
<img width="300" height="300" src="https://raw.githubusercontent.com/radnive/Flutter_DashedCircularProgressBar/main/example/simple_example.gif" alt="simple_example_gif">

First of all, to access the amount of progress when doing animation, you need to define a **ValueNotifier**:

```dart
final ValueNotifier<double> _valueNotifier = ValueNotifier(0);
```

Then add it to the widget:

```dart
DashedCircularProgressBar.aspectRatio(
  aspectRatio: 1, // width ÷ height
  valueNotifier: _valueNotifier,
  progress: 478,
  maxProgress: 670,
  corners: StrokeCap.butt,
  foregroundColor: Colors.blue,
  backgroundColor: const Color(0xffeeeeee),
  foregroundStrokeWidth: 36,
  backgroundStrokeWidth: 36,
  animation: true,
  child: Center(
    child: ValueListenableBuilder(
      valueListenable: _valueNotifier,
      builder: (_, double value, __) => Text(
        '${value.toInt()}%',
        style: const TextStyle(
          color: Colors.black,
          fontWeight: FontWeight.w300,
          fontSize: 60
        ),
      ),
    ),
  ),
)
```

### Example 2 - Dashed background progress bar
<img width="300" height="160" src="https://raw.githubusercontent.com/radnive/Flutter_DashedCircularProgressBar/main/example/dashed_background_example.gif" alt="simple_example_gif">

```dart
DashedCircularProgressBar.aspectRatio(
  aspectRatio: 2, // width ÷ height
  progress: 34,
  startAngle: 270,
  sweepAngle: 180,
  circleCenterAlignment: Alignment.bottomCenter,
  foregroundColor: Colors.black,
  backgroundColor: const Color(0xffeeeeee),
  foregroundStrokeWidth: 3,
  backgroundStrokeWidth: 2,
  backgroundGapSize: 2,
  backgroundDashSize: 1,
  seekColor: Colors.yellow,
  seekSize: 22,
  animation: true,
)
```

### Example 3 - More complex progress bar
<img width="300" height="305" src="https://raw.githubusercontent.com/radnive/Flutter_DashedCircularProgressBar/main/example/more_complex_example.gif" alt="more_complex_example_gif">

```dart
DashedCircularProgressBar.aspectRatio(
  aspectRatio: 1, // width ÷ height
  valueNotifier: _valueNotifier,
  progress: 37,
  startAngle: 225,
  sweepAngle: 270,
  foregroundColor: Colors.green,
  backgroundColor: const Color(0xffeeeeee),
  foregroundStrokeWidth: 15,
  backgroundStrokeWidth: 15,
  animation: true,
  seekSize: 6,
  seekColor: const Color(0xffeeeeee),
  child: Center(
    child: ValueListenableBuilder(
      valueListenable: _valueNotifier,
      builder: (_, double value, __) => Column(
        mainAxisSize: MainAxisSize.min,
        children: [
          Text(
            '${value.toInt()}%',
            style: const TextStyle(
              color: Colors.black,
              fontWeight: FontWeight.w300,
              fontSize: 60
            ),
          ),
          Text(
            'Accuracy',
            style: const TextStyle(
              color: Color(0xffeeeeee),
              fontWeight: FontWeight.w400,
              fontSize: 16
            ),
          ),
        ],
      )
    ),
  ),
)
```

### Example 4 - Dashed progress bar

You can also use the desired dimensions instead of aspect ratio.

<img width="300" height="300" src="https://raw.githubusercontent.com/radnive/Flutter_DashedCircularProgressBar/main/example/dashed_example.gif" alt="dashed_example_gif">

```dart
DashedCircularProgressBar.square(
  dimensions: 350,
  progress: 180,
  maxProgress: 360,
  startAngle: -27.5,
  foregroundColor: Colors.redAccent,
  backgroundColor: const Color(0xffeeeeee),
  foregroundStrokeWidth: 7,
  backgroundStrokeWidth: 7,
  foregroundGapSize: 5,
  foregroundDashSize: 55,
  backgroundGapSize: 5,
  backgroundDashSize: 55,
  animation: true,
  child: const Icon(
    Icons.favorite,
    color: Colors.redAccent,
    size: 126
  ),
)
```

### Example 5 - Play with circle center alignment
By changing the center, you can specify the location of the progress bar.

![play_with_circle_center_alignment_example.png](https://raw.githubusercontent.com/radnive/Flutter_DashedCircularProgressBar/main/example/play_with_circle_center_alignment_example.png)

For example to make a progress bar in the shape of the first image (first row, first image from the left):

```dart
DashedCircularProgressBar.aspectRatio(
  aspectRatio: 1, // width / height
  progress: 60,
  startAngle: 90,
  sweepAngle: 90,
  corners: StrokeCap.butt,
  foregroundStrokeWidth: 7,
  backgroundStrokeWidth: 7,
  circleCenterAlignment: Alignment.topLeft,
  foregroundColor: Colors.white,
  backgroundColor: const Color(0x22000000),
  animation: true
)
```
