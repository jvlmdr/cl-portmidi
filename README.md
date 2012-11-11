# portmidi

PortMidi bindings for Common Lisp using CFFI

Loadable as "portmidi" via ASDF / Quicklisp (as a local project)

## Status

The library is usable so far, almost all functions are implemented (except for filtering).

I'm currently working on a more convenient interface.

## Example:

```lisp
(ql:quickload "portmidi")
(defvar *midi-out* (pm:open-output (pm:get-default-output-device-id) 1024 0))
(pm:write-short-midi *midi-out* 0 (pm:note-on 0 80))
(pm:write-short-midi *midi-out* 0 (pm:note-off 0 80))
(pm:close-midi *midi-out*)
```