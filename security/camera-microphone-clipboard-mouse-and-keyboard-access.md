# Camera, microphone, clipboard, mouse, and keyboard access

<div>

When a SWF file attempts to access a user's camera or microphone using the
`Camera.get()` or `Microphone.get()` methods, Flash Player displays a Privacy
dialog box, in which the user can allow or deny access to their camera and
microphone. The user and the administrative user can also disable camera access
on a per-site or global basis, through controls in the mms.cfg file, the
Settings UI, and the Settings Manager (see
[Administrator controls](WS5b3ccc516d4fbf351e63e3d118a9b90204-7c95.html) and
[User controls](WS5b3ccc516d4fbf351e63e3d118a9b90204-7c91.html)). With user
restrictions, the `Camera.get()` and `Microphone.get()` methods each return a
`null` value. You can use the `Capabilities.avHardwareDisable` property to
determine whether the camera and microphone have been administratively
prohibited ( `true`) or allowed ( `false`).

The `System.setClipboard()` method allows a SWF file to replace the contents of
the clipboard with a plain-text string of characters. This poses no security
risk. To protect against the risk posed by passwords and other sensitive data
being cut or copied to clipboards, there is no corresponding `getClipboard()`
method.

An application running in Flash Player can monitor only keyboard and mouse
events that occur within its focus. Content running in Flash Player cannot
detect keyboard or mouse events in another application.

</div>

<div>

<div>

</div>

</div>
