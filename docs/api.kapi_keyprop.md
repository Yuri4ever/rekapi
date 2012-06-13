# Kapi.KeyframeProperty

````javascript
/**
 * @param {Kapi.Actor} ownerActor The Actor to which this KeyframeProperty is
 *     associated.
 * @param {number} millisecond Where in the animation this KeyframeProperty
 *     lives.
 * @param {string} name The property's name, such as "x" or "opacity."
 * @param {number} value The value of `name`.  This is the value to animate to.
 * @param {string=} opt_easing The easing to arrive to `value` at.  Defaults to
 *     linear.
 * @constructor
 */
Kapi.KeyframeProperty (ownerActor, millisecond, name, value, opt_easing)
````
Represents an individual component of an `Actor`'s keyframe state.  In most
cases you won't need to deal with this directly, `Actor` abstracts a lot of
what this Object does away for you.


### modifyWith

````javascript
/**
 * @param {Object} newProperties Contains the new `millisecond`, `easing`, or
 *     `value` values to update this KeyframeProperty with.  These correspond
 *     to the formal parameters of the KeyframeProperty constructor.
 */
Kapi.KeyframeProperty.prototype.modifyWith (newProperties)
````

Augment a `KeyframeProperty`'s properties.


### linkToNext

````javascript
/**
 * @param {KeyframeProperty} nextProperty The KeyframeProperty that immediately
 *     follows this one in an animation.
 */
Kapi.KeyframeProperty.prototype.linkToNext (nextProperty)
````

Create the reference to the next KeyframeProperty in an `Actor`'s
`KeyframeProperty` track.


### getValueAt

````javascript
/**
 * @param {number} millisecond The point in the animation to compute the
 *     midpoint of the two KeyframeProperties.
 * @return {number}
 */
Kapi.KeyframeProperty.prototype.getValueAt (millisecond)
````

Calculate the midpoint between this `KeyframeProperty` and the next
`KeyframeProperty` in an `Actor`'s `KeyframeProperty` track.


### exportTimeline

````javascript
/**
 * @return {Object}
 */
Kapi.KeyframeProperty.prototype.exportTimeline ()
````

Export a reference-less dump of this KeyframeProperty's state data.
