# Malarkey.js [![npm Version](http://img.shields.io/npm/v/malarkey.svg?style=flat)](https://www.npmjs.org/package/malarkey)

> Simulate a typewriter/ticker effect on a DOM element.

## Usage

```html
<body>
  <div class="malarkey"></div>
  <script src="dist/malarkey.min.js"></script>
  <script>
    var elem = document.querySelectorAll('.malarkey')[0];
    var opts = {
      speed: 100,
      loop: true,
      postfix: ''
    };
    malarkey(elem, opts).type('Say hello')   .pause(2000).delete()
                        .type('Wave goodbye').pause(2000).delete();
  </script>
</body>
```

## API

### malarkey(elem, opts)

Initialises the typewriter/ticker effect on `elem` with the given `opts` settings.

- `elem` is a DOM element.

- `opts` is an object literal. Settings include:
  - `speed` &mdash; Number of milliseconds to type or delete a single character. Defaults to `100`.
  - `loop` &mdash; Whether to repeat the entire sequence. Defaults to `false`.
  - `postfix` &mdash; This is appended to all strings passed to the `type` method. Defaults to `''`.

### malarkey.type(str [, speed])

Types the given `str`. If specified, `speed` (in milliseconds) overrides `opts.speed`.

### malarkey.delete(str [, speed])

- If `str` is a number, at most that many characters are deleted from the DOM element.
- Otherwise, if the last string typed ends with `str`, then said `str` is deleted from the DOM element.

If specified, `speed` (in milliseconds) overrides `opts.speed`.

### malarkey.pause(duration)

Do nothing for the given `duration` (in milliseconds).

### malarkey.clear()

Clears the contents of the DOM element.

## License

[MIT license](https://github.com/yuanqing/malarkey/blob/master/LICENSE)
