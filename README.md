# bubble-stick

Some libraries (like Salesforce.com) promote making events not bubble by default.  This can be problematic when dealing with large numbers of such elements.  Some recent internal components also don't bubble, such as the [detail's toggle event](https://github.com/whatwg/html/issues/1533).

This is an especially challenging issue when there are multiple libraries at work unaware of each other.  One library may be responsible for expanding large numbers of detail elements (say "expand all").  Another library may be dynamically inserting / deleting, or hiding / showing (nested) detail elements ( say when doing "searches" of a large volume of articles like all mathematics articles).  Another library may be focused on persisting user settings, i.e. remembering which detail elements were opened, etc.  The fact that the toggle event doesn't bubble would seem to require that these separate "concerns" must be centrally managed with tightly coupled components.

bubble-stick's purpose is to "centralize" the pain, and to "enhance" native or custom elements with bubbling (even composing) events.

