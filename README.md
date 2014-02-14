Class_CtlColors
===============

Choose your own background and/or text colors for some AHK GUI controls.

## How to use ##

- To register a control for coloring call `CtlColors.Attach()` passing up to three parameters:
    ```
    HWND    - HWND of the GUI control
    BkColor - HTML color name, 6-digit hexadecimal RGB value, or "" for default color
    ------- Optional 
    TxColor - HTML color name, 6-digit hexadecimal RGB value, or "" for default color
    ```
    If both BkColor and TxColor are "" the control will not be added and the call returns False.

- To change the colors for a registered control call `CtlColors.Change()` passing up to three  parameters:
    ```
    HWND    - see above
    BkColor - see above
    ------- Optional
    TxColor - see above
    ```
    Both BkColor and TxColor may be "" to reset them to default colors.
    If the control is not registered yet, `CtlColors.Attach()` is called internally.

- To unregister a control from coloring call `CtlColors.Detach()` passing one parameter:
    ```
    HWND    - see above
    ```

- To stop all coloring and free the resources call `CtlColors.Free()`.
It's a good idea to insert this call into the scripts exit-routine.

- To check if a control is already registered call `CtlColors.IsAttached()` passing one parameter:
    ```
    HWND    - see above
    ```

To get a control's HWND use either the option `HwndOutputVar` with `Gui, Add` or the command `GuiControlGet` with sub-command `Hwnd`.
