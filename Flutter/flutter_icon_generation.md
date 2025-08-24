
# Flutter アプリアイコン生成方法

Flutter で Android / iOS の **アプリアイコン**を自動生成するための手順です。
`flutter_launcher_icons` パッケージを使います。

---

## 1. flutter_launcher_icons とは
- Android と iOS 両方のアイコン画像を、**1枚の画像から自動生成**するツールです。
- 通常は解像度ごとに複数のアイコンを作る必要がありますが、これを自動でやってくれます。

---

## 2. セットアップ方法

`pubspec.yaml` に以下を追記します：

```yaml
dev_dependencies:
  flutter_launcher_icons: ^0.13.1

flutter_icons:
  android: true
  ios: true
  image_path: "assets/icon.png"
```

### 設定項目
- **android**: Android 用アイコンを生成するかどうか
- **ios**: iOS 用アイコンを生成するかどうか
- **image_path**: 元となるアイコン画像のパス（推奨: 1024x1024px の PNG）

---

## 3. コマンドの実行

以下を実行してアイコンを生成します：

```bash
dart run flutter_launcher_icons:main
```

### コマンドの意味
- `dart run` → Dart のパッケージを直接実行
- `flutter_launcher_icons:main` → アイコン生成処理を呼び出す

---

## 4. 実行結果

- **Android** → `android/app/src/main/res/mipmap-*` のアイコンが置き換わります
- **iOS** → `ios/Runner/Assets.xcassets/AppIcon.appiconset/` に新しいアイコンが配置されます

---

## 5. 実行後の推奨手順

```bash
flutter clean
flutter pub get
flutter run
```

これで、新しいアイコンが反映されたアプリを実機で動かせます。

---

## まとめ

| 項目                | 内容                                  |
|---------------------|--------------------------------------|
| パッケージ          | `flutter_launcher_icons`             |
| 設定ファイル        | `pubspec.yaml` に設定を書く          |
| 実行コマンド        | `dart run flutter_launcher_icons:main` |
| 出力場所 (Android)  | `android/app/src/main/res/mipmap-*`  |
| 出力場所 (iOS)      | `ios/Runner/Assets.xcassets/AppIcon.appiconset/` |

この手順で、Flutter アプリのアイコンを簡単に生成・更新できます。
