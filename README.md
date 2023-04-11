This theme is for a e ink tablet.

3. format required: {}, or [], or "", they diff
4. file name suffix effects whether the theme works.

`"type" = { fg = "red", bg = "yellow" }`

1. primitives
2. other complex type, in different positions
    1. ![image](https://user-images.githubusercontent.com/130418928/231193939-dd662843-ebd7-4801-9c84-5123e376bfbc.png)
    2. impl, enum, struct, trait, return type of fn, parameter type...
3. In different positions, under different willing, maybe its n-lvl common part(type, according to variable) need to be bold or normal or only indicate its difference(when? with name? with other environment?), same on its variable name.

1. helix theme is not finished or enough.
2. bold the type, or darker bg the type(easy to mix with cursor, deny)
3. italic => variable, changeable, free
5. modifiers
    5. "underline", types.
    7. NOT available on e ink tablet
        6. "dim", use gray/light-gray instead.
        9. "slow_blink", only works on myPC
        10. "rapid_blink"
        12. "hidden"
    13. "crossed_out",only for
12. underline
    1. syntax: is with `{}`
    2. color, NOT work.
    3. style, all NOT work.
13. color, only support base64 in my eink pad. pallete failed. e.g. #982332
    1. green, like dim, if bg==black, its dim is more clear.
    2. red, blue... works similar, not good as gray. if wanna dim, choose gray. light-red, light-gray... are trivial diff.
    3. let those color to be used as bg.

```
# Author : ghc0 publj@outlook.com

# underline
    # meta
        # Most of its colors or styles are unavailable on my e ink tablet, there fore only left 1 simple underline.
        # underline is unclean, restrict its amount.
    # Without underline, for PLAIN TEXT.
    # With underline, for rare RETURN.
# modifiers
    # crossed_out
        # Without crossed_out, for PLAIN TEXT.
        # With crossed_out, for DIAGNOSTIC, multi-CURSORS.
    # bold
        # Without bold, for PLAIN TEXT.
        # With bold, too dim, keep it for nothing.
    # italic
        # Without italic, for PLAIN TEXT.
        # With italic, for  KEYWORDS.
    # reversed
        # Without reversed, for PLAIN TEXT.
        # With reversed? I prefer to manually define its fg/bg colors.
# fg/bg with color
    # on my e ink tablet, only 16 colors are supported, and most of them acts the same, therefore I choose main 4 colors.
    # black
        # With black
            # With fg, for PLAIN TEXT.
            # With bg, for CURSOR.
        # Without black
    # white
        # With white
            # With fg, for CURSOR.
            # With bg, for PLAIN TEXT.
        # Without white
    # gray
        # With gray
            # With fg, is similar effect as BOLD on my e ink tablet, keep it for nothing.
            # With bg, for SELECTION.
        # Without gray
    # light-gray
        # With light-gray
            # With fg, for COMMENTS.
            # With bg, for ???, is easily confused with SELECTIONS and CURSORS, keep it for nothing if CURSORS are in working.
        # Without light-gray


"ui.selection" = { fg = "white", bg = "gray" }
"ui.cursor.primary" = { fg = "white", bg = "black" }
"ui.cursor" = { fg = "white", bg = "black", modifiers = ["crossed_out"] }
"ui.cursor.match" = { modifiers = ["bold", "crossed_out"] }

"ui.background" = { fg = "black", bg = "white" }
"ui.linenr.selected" = { fg = "white", bg = "light-gray", underline = { style = "line" } }
"ui.statusline" = { fg = "white", bg = "black" }

"diagnostic" = { fg = "white", bg = "light-gray", modifiers = ["crossed_out"] }
"warning" = { fg = "white", bg = "gray", modifiers = ["bold"] }
"error" = { fg = "white", bg = "black", modifiers = ["bold"] }
"info" = { fg = "white", bg = "light-gray", modifiers = ["bold"] }
"hint" = { fg = "white", bg = "light-gray", modifiers = ["bold", "italic"] }

"keyword" = { modifiers = ["italic"] }
"type" = { underline = { style = "line" }, modifiers = ["bold"] }
"comment" = { fg = "gray", modifiers = ["italic"] }
"keyword.control.return" = { fg = "white", bg = "light-gray" }

```
