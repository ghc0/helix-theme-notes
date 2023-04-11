# helix-theme-notes

notes of how to build helix theme

It contains 2 structures: 
I. what&where
II. effects

If you care dependencies in contents(terms&pictures), pls **read from start to end**. Or if you know what you are doing, just **Ctrl-s** or **read anywhere**.

time: 20230411-?

## I. What&where?

### I.a obligingness

> I don't know why but this one is necessary, if not, error.

#### I.a.1 `"ui.selection" = { fg = "red", bg = "green" }`

![image](https://user-images.githubusercontent.com/130418928/231174692-54f85b18-a355-4950-8510-a58f7878f7a7.png)

1. Selection is diff from a cursors[?], but it contains cursors[?]. So if you press `e`, it usually `red` lots of chars of text.
2. priority when selection meet cursor[?] ?
3. will it affect underline?
4. what if combine the effects to create new effect!
5. foreground, fg, where is it?
6. background, bg, where is it?

### I.b optional

#### I.b.1 `"attribute" = { fg = "blue", modifiers = ["bold"] }`

![image](https://user-images.githubusercontent.com/130418928/231178700-40aacc64-fbc5-4758-9237-679e8f432713.png)

1. `attribute` only contains key, doesn't contains `=` or `value`
2. `attribute` contains class attributes and HTML attributes, where is `class attribute`? Well, rust doesn't contain class...
3. "bold": diff between "l" in "html" and "l" in "class"
4. Don't forget add `[]` after `modifiers = `. Though `modifiers` contains only one element, its general logic is to contain a `set`, accidently, in this case, the `set` only contains one element.
5. If name of file is not end with `.html`, the `attribute` won't be painted like what you configed.

#### I.b.2 `"type" = { fg = "red", bg = "yellow" }`

1. primitives
![image](https://user-images.githubusercontent.com/130418928/231193203-98ca59f5-3d2d-4fa0-bca7-df857807c430.png)
2. other complex type, different positions
    1. ![image](https://user-images.githubusercontent.com/130418928/231193939-dd662843-ebd7-4801-9c84-5123e376bfbc.png)
    2. impl ![image](https://user-images.githubusercontent.com/130418928/231194202-f8c745ac-6083-4fb5-83b6-556d3882945d.png)
    3. enum ![image](https://user-images.githubusercontent.com/130418928/231193630-20d49b98-58f4-455f-a924-576eac496a73.png)
    4. struct ![image](https://user-images.githubusercontent.com/130418928/231193445-7f526666-bdb9-42ec-8623-a9e5a8d45599.png)
    5. trait, return type of fn, parameter type...
3. sometimes its type part of value do matters, sometimes its personal detail part of value do matters. Type, is diff-lvl of abstraction. When do we need to `bold` it? or paint it in other way? or just make it different from its name? Since rust put the type after the name, it is the name instead the type need to be bold.

`"ui.background" = { fg = "red", bg = "green" }`

1. What is `"ui.background"`
2. What is its `fg` and `bg`

![image](https://user-images.githubusercontent.com/130418928/231032263-cde307fa-4bb7-4cba-975c-4a06b0b5c473.png)

### 2. `"attribute" = { fg = "red", bg = "green", modifiers = ["bold", "italic"] }`

1. the range of attribute
2. what's modifiers_bold
3. what's modifiers_italic

![image](https://user-images.githubusercontent.com/130418928/231157197-9f296ee0-efad-484b-bb94-63a0b35c5d90.png)

## 2. Effects

### 1. modifiers = ["slow_blink"]

1. unavailable on eink pad
2. available on PC
    1. works on only text(not contain underline)

![tmp](https://user-images.githubusercontent.com/130418928/231166337-590b8985-e7c0-4e11-b20a-499570176e62.gif)
