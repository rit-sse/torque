torque
======

A polymer based automated slide show.

## Usage

In you project directory run

```
bower install --save rit-sse/torque
```

Import the

```html
  <link rel="import" href="bower_components/torque/torque-slides.html">
```

And you should be ready to go

### [Example](http://rit-sse.github.io/torque/)
```html
<torque-slides duration="1">
  <torque-slide duration="6">
    Wow!
  </torque-slide>
  <torque-slide>
    Check out
  </torque-slide>
  <torque-slide>
    My Cool
  </torque-slide>
  <torque-slide>
    Unstyled
  </torque-slide>
  <torque-slide>
    Torque slides!
  </torque-slide>
</torque-slides>
```

### Overview
The above example is relatively simple. But just to explain some of the features:

Torques slides transition in order starting with the first `torque-slide`. When it get's to the end, it will go back to the beginnning. `duration` is specified in seconds at the `torque-slides` level but can be overiddden at the `torque-slide` level. 

Something that you can't really see from this example, a `torque-slide` can be nested in other elements and it will still work.  So for example this will still work:

```html
<torque-slides duration="1">
  <div class="thing">
    <torque-slide duration="6">
      Wow!
    </torque-slide>
    <torque-slide>
     Check out
    </torque-slide>
  </div>
  <torque-slide>
    My Cool
  </torque-slide>
  <torque-slide>
    Unstyled
  </torque-slide>
  <torque-slide>
    Torque slides!
  </torque-slide>
</torque-slides>
```

Another feature that is not shown is that there is an event fired on all children when the slide is displayed.

**index.html**
```html
<torque-slides duration="1">
  <torque-slide duration="6">
    <my-slide-data></my-slide-data>
  </torque-slide>
</torque-slides>
```

**my-slide-data.html**

```html
<polymer-element name="my-slide-data" on-no-longer-hidden="{{myHandlerFunction}}">
....
</polymer-element>
```

That's about it.
