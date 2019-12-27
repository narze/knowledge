---
description: Tips & Tricks
---

# Karabiner Elements

## Goku

\[Goku\]\([https://github.com/yqrashawn/GokuRakuJoudo](https://github.com/yqrashawn/GokuRakuJoudo)\) makes configuration shorter & easier \(once you know the syntax\), it converts Goku's DSL in `edn` format to `karabiner.json`

The downside on using Goku is it will overwrite the whole `karabiner.json` file. If you already configured some rules in json you'll have to convert it to Goku's DSL.

## Using other keyboard layout \(Non Qwerty\)

Since Karabiner Elements modifies keys at the low-level, it will have some issues with non-qwerty layouts. For example, if I want to swap `;` and `:` then I have to map the `P` key instead since typing `;` uses the physical key `P` on standard layout. To write this rule in Goku, use `:input-sources` to filter the rule and use physical key instead.

```text
:input-sources {:colemak {:input_source_id "com.apple.keylayout.Colemak"
                           :language "en"}}
 :main [
        ; For Qwerty 
        {:des "; <-> : (Qwerty)" :rules [[:semicolon :!Ssemicolon] [:!Ssemicolon :semicolon]]}
        : p maps to ; on Colemak, so map p instead only in Colemak
        {:des "; <-> : (Colemak)" :rules [:colemak [:p :!Sp] [:!Sp :p]]}
        ]
```

