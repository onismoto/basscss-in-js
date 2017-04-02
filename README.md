# basscss-in-js

Atomic CSS means writing single-purpose classes and composing them at the point of use. You can read about the benefits of this approach at the links below:

- [Functional Programming, CSS, and your sanity](http://www.jon.gold/2015/07/functional-css/)
- [CSS and Scalability](http://mrmrs.io/writing/2016/03/24/scalable-css/)

[Basscss](http://basscss.com/) is a good place to start. It provides a useful collection of classes that do one thing and do it well, and it's documentation is top-notch. However, it probably won't provide everything you'll ever need or want from CSS. At some point you may want to augment it with your own classes or mix it with those provided by other collections. That means you have to worry about naming clashes and losing track of dependencies. These are problems that already have solutions in JavaScript. 

This is a port of Basscss to JavaScript. Instead of this:
```css
.h1 {
  font-size: 2rem
}
```

You have this:
```javascript
export const h1 = {
  fontSize: '2rem'
}
```

And it's used like this (in React for example):
```javascript
import { h1, right_align } from 'basscss-in-js'
import { btn } from 'some-other-library'
import { green } from './colors'

const myComponent = () => 
  <button style={{
    ...h1,
    ...right_align,
    ...btn,
    ...green,
  }}>Continue</button>
```
