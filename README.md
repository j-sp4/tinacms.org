# TinaCMS.org

Source code for the tinacms.org website.

[![deepcode](https://dchook.eu.ngrok.io/api/gh/badge?secretKey=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1OTM3Njk4MDF9.P5HYdqhUrZJK4FMUGL0He1Bf17tLZiDmI3kbuIJVZ8o)](https://deepcode.ai)

## Development

```
yarn install
yarn develop
```

### Testing Local TinaCMS Changes

If you have the **tinacms** repository cloned locally you can use it when running **tinacms.org**:

```
TINA=../path/to/tinacms yarn develop
```

You can also specify which packages you want to watch:

```
TINA=../path/to/tinacms TINA_WATCH=@tinacms/forms,react-tinacms-inline
```

## Shortcodes

This site supports shortcodes in Markdown content via [remark-shortcodes](https://github.com/djm/remark-shortcodes).

Shortcodes must be written as React components. To add a shortcode, export it from `utils/shortcodes.tsx`.

```jsx
export function MyShortcode({ textContent }) {
  return <div>{textContent}</div>
}
```

Call the shortcode in your content by writing the name of the component encased in double curly braces. Key-value pairs included in the shortcode will be passed to your component as props.

```
{{ MyShortcode textContent="Example shortcode" }}
```

### Shortcode Limitations

Shortcodes must be standalone elements; "wrapping" shortcodes will not work.
