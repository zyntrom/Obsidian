## 🌟 What You’ll Learn

- `flex-grow`: distribute **extra** space
- `flex-shrink`: control how items **shrink**
- `flex-basis`: set **initial size**
- `flex`: shorthand for all three
- `order`: rearrange item **positions**

---

## 🔼 1. `flex-grow`: Who gets the extra space?

- Controls how much an item **grows** if extra space is available.
- Default is `0` (does **not** grow).

```css
.item {   flex-grow: 1; /* all items share space equally */ }
```

If:

```css
.item-1 { flex-grow: 2; } .item-2 { flex-grow: 1; }
```

→ Item 1 gets **2x** more extra space than Item 2.

---

## 🔽 2. `flex-shrink`: Who shrinks when space is tight?

- Controls how much an item **shrinks** when there’s **not enough space**.
- Default is `1` (can shrink).

```css
.item {   flex-shrink: 1; }
```

If:

```css
.item-1 { flex-shrink: 2; } .item-2 { flex-shrink: 1; }
```

→ Item 1 shrinks **twice as fast**.

---

## 📏 3. `flex-basis`: Starting size of the item

- Sets the **initial** width/height before grow or shrink is applied.

```css
.item {   flex-basis: 200px; }
```

Can be in `px`, `%`, `em`, or `auto`.

---

## ✂️ 4. `flex`: Shorthand for all three

```css
.item {   flex: <flex-grow> <flex-shrink> <flex-basis>; }
```

### Common Shorthand Examples:

|Shorthand|Equivalent|Meaning|
|---|---|---|
|`flex: 1`|`1 1 0`|Grows & shrinks, base 0|
|`flex: 0`|`0 1 0`|No grow, can shrink|
|`flex: auto`|`1 1 auto`|Grow/shrink based on content size|
|`flex: none`|`0 0 auto`|Fixed size, no grow or shrink|
|`flex: 2 1 100px`|custom|Grows 2x, shrinks, base 100px|

---

## 🔢 5. `order`: Control display order (not based on HTML)

css

CopyEdit

```css
.item {   order: 2; /* default is 0 */ }
```

Lower `order` value appears **first**. Use to reorder elements **visually** without changing HTML.

---

## 🎯 Final Example

```css
.item {   flex: 2 1 150px;   order: 1; }
```

- Grows a lot
- Shrinks if needed
- Starts at 150px
- Appears after `order: 0` items

---

## ✅ Summary Table

| Property      | Purpose                                   |
| ------------- | ----------------------------------------- |
| `flex-grow`   | How much to grow when space is free       |
| `flex-shrink` | How much to shrink when space is tight    |
| `flex-basis`  | Starting (initial) size of the item       |
| `flex`        | Shorthand for grow, shrink, and basis     |
| `order`       | Rearranges item visually in the container |