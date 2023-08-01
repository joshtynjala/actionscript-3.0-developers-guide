# Getting the current Stage orientation and aspect ratio

Orientation is reported relative to the normal position of the device. On most
devices there is a clear, upright position. This position is considered the
_default_ orientation. The other three possible orientations are then: _rotated
left_, _rotated right_, and _upside down_. The StageOrientation class defines
string constants to use when setting or comparing orientation values.

The Stage class defines two properties that report orientation:

- Stage.deviceOrientation — Reports the physical orientation of the device
  relative to the default position. Note: The deviceOrientation is not always
  available when your application first starts up or when the device is lying
  flat. In these cases, the device orientation is reported as _unknown_.

- Stage.orientation — Reports the orientation of the Stage relative to the
  default position. When auto-orientation is enabled, the stage rotates in the
  opposite direction as the device to remain upright. Thus, the right and left
  positions reported by the `orientation` property are the opposite of those
  reported by the `deviceOrientation` property. For example, when
  `deviceRotation` reports _rotated right_, `orientation` reports _rotated
  left_.

The aspect ratio of the stage can be derived by simply comparing the current
width and height of the stage:

    var aspect:String = this.stage.stageWidth >= this.stage.stageHeight ? StageAspectRatio.LANDSCAPE : StageAspectRatio.PORTRAIT;
