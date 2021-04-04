# MelonPreferencesManager

In-game UI for managing MelonLoader Mod Preferences. Supports IL2CPP and Mono Unity games.

Requires MelonLoader 0.3.1+ (currently you must build this version yourself, otherwise wait for the release).

* [Download (IL2CPP)](https://github.com/sinai-dev/MelonPreferencesManager/releases/latest/download/MelonPrefManager.IL2CPP.zip)
* [Download (Mono)](https://github.com/sinai-dev/MelonPreferencesManager/releases/latest/download/MelonPrefManager.Mono.zip)

[![](img/preview.png)](https://raw.githubusercontent.com/sinai-dev/MelonPreferencesManager/master/img/preview.png)

## Info for developers

The UI supports the following types:

* Toggle: `bool`
* Number input: `int`, `float`, etc (NOTE: `decimal` is **not** supported by MelonLoader currently)
* String input: `string`
* Color editor: `Color`
* Struct editor: `Vector2`, `Vector3`, `Vector4`, `Rect`
* Toml input: Anything with a corresponding Mapper registered to `MelonPreferences.Mapper`.

To make a slider, use a number type and provide a `ValueRange` for the Validator when creating the entry.

You can register a custom UI handler for a Type, to override the default Toml input editor for it.
* Define a `MyIValueType : InteractiveValue` class (refer to existing classes for examples)
* Call `InteractiveValue.RegisterIValueType<MyIValueType>();`
* Note: If the Type is already handled by an existing InteractiveValue, your one will not be used.
