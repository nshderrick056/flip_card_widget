# Guess the Car

A Flutter flashcard quiz: see a car photo, guess it, tap to flip the card, then mark whether you got it right.

## Features
- Six cars, shuffled every game
- 3D flip animation between the photo and the answer
- Live score, with a results dialog and **Play again** at the end of the deck
- Cards without a photo show a car icon instead

## Getting started
You need the [Flutter SDK](https://docs.flutter.dev/get-started/install) (Dart 3 or newer).

```bash
flutter pub get
flutter run
```

To run the tests:

```bash
flutter test
```

## How to play
1. Look at the photo and guess the car.
2. Tap the card to see its name and a fact.
3. Choose **Got it right** or **Got it wrong**.
4. Choose **Next car** to continue.

## Project structure
All the app code is in `lib/main.dart`:

| Part | What it does |
|---|---|
| `Car`, `cars` | The car data: name, image path and fact |
| `FlashcardScreen` | The game screen: deck, score and current card |
| `FlipCard` | Animates the flip using `TweenAnimationBuilder` and `Transform` |
| `_CardFront`, `_CardBack` | The photo side and the answer side |

Photos are in `assets/`, and the tests are in `test/widget_test.dart`.

## Adding a car
1. Put the photo in `assets/`, for example `assets/honda_civic.jpg`.
2. Add a line to the `cars` list in `lib/main.dart`:

   ```dart
   Car('Honda Civic', 'assets/honda_civic.jpg', 'Your fact here.'),
   ```

3. Stop the app and run it again, because hot reload doesn't pick up new assets.
