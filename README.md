![Image](/img/1100x330.png)


Fluent API wrapper for Android Espresso :coffee:

**Check out my [blog](https://medium.com/@blipinsk) :squirrel: or say *hi* on [Twitter](https://twitter.com/blipinsk).**

--------

Overview
--------
Cortado provides a layer of abstraction above Espresso, so it's a bit easier to use.

**Remember: It is Google Espresso underneath.** You can still mess up your tests the same way you would when using pure Espresso. Cortado just gives you a bit nicer way to communicate with Espresso.

Comparison
==========

1. Get a `Matcher` for `clickable` views with `R.id.text`

  Framework | Code example
  --- | ---
  Espresso | `Matchers.allOf(withId(R.id.text), isClickable());`
  Cortado | `Cortado.view().withId(R.id.text).and().isClickable();`

2. Get a `Matcher` for views that have text `example` or have parent `FrameLayout`

  Framework | Code example
  --- | ---
  Espresso | `Matchers.anyOf(withText("example"), withParent(isAssignableFrom(FrameLayout.class)));`
  Cortado | `Cortado.view().withText("example").or().withParent(isAssignableFrom(FrameLayout.class));`

3. Click on a `View` with `R.id.button`

  Framework | Code example
  --- | ---
  Espresso | `Espresso.onView(withId(R.id.button)).perform(ViewActions.click());`
  Cortado | `Cortado.onView().withId(R.id.button).perform().click();`

4. Check if a `View` with text `example` is visible

  Framework | Code example
  --- | ---
  Espresso | `Espresso.onView(withText("example")).check(ViewAssertions.matches(isDisplayed()));`
  Cortado | `Cortado.onView().withText("example").check().matches(isDisplayed());`

5. Replace a text on `enabled` view with `R.id.edit`

  Framework | Code example
  --- | ---
  Espresso | `Espresso.onView(Matchers.allOf(withId(R.id.edit),isEnabled())).perform(ViewActions.replaceText("changed"));`
  Cortado | `Cortado.onView().withId(R.id.edit).and().isEnabled().perform().replaceText("changed");`

Including In Your Project
-------------------------

```xml
dependencies {
    compile 'com.bartoszlipinski:cortado:1.0.1'
}
```

Developed by
============
 * Bartosz Lipiński

License
=======

    Copyright 2017 Bartosz Lipiński

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
