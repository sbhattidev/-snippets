                           ┌───────────────────────┐
                           │     MaterialApp       │
                           │ (root of the widget   │
                           │        tree)          │
                           └─────────┬─────────────┘
                                     │
                           ┌─────────▼─────────────┐
                           │       Scaffold        │
                           │ (screen structure)    │
                           └─────────┬─────────────┘
         ┌───────────────────────────┼────────────────────────────┐
         │                           │                            │
   ┌─────▼─────┐              ┌──────▼─────┐              ┌───────▼────────┐
   │   AppBar  │              │    Body    │              │ BottomNavBar   │
   └───────────┘              └──────┬─────┘              └────────────────┘
                                     │
                            ┌────────▼─────────┐
                            │   Layout Widgets │
                            └────────┬─────────┘
             ┌───────────────────────┼───────────────────────┐
             │                       │                       │
     ┌───────▼───────┐       ┌───────▼───────┐       ┌───────▼───────┐
     │   Column      │       │     Row       │       │    Stack      │
     └───────┬───────┘       └───────┬───────┘       └───────┬───────┘
             │                       │                       │
   ┌─────────▼────────┐     ┌────────▼────────┐     ┌────────▼────────┐
   │ Child Widgets    │     │ Child Widgets   │     │ Positioned, etc │
   └─────────┬────────┘     └────────┬────────┘     └─────────────────┘
             │                       │
   ┌─────────▼────────┐     ┌────────▼────────┐
   │ UI Widgets       │     │ Interactive     │
   └─────────┬────────┘     └────────┬────────┘
             │                       │
   ┌─────────▼──────────┐   ┌────────▼─────────┐
   │ Text, Icon, Image  │   │ ElevatedButton   │
   │ Container, Card    │   │ GestureDetector  │
   │ ListView, GridView │   │ InkWell, Switch  │
   └────────────────────┘   └──────────────────┘


 Other Scaffold slots:
 ┌─────────────────────┐
 │ FloatingActionButton│
 │ Drawer              │
 │ SnackBar / BottomSheet
 │ TabBar / TabView
 └─────────────────────┘


 State Management Layer:
 ┌─────────────────────┐
 │ StatefulWidget      │
 │ StatelessWidget     │
 │ InheritedWidget     │
 │ Provider / Riverpod │
 └─────────────────────┘


 Rendering Pipeline:
 ┌─────────────────────┐
 │ Widget Tree         │
 │ → Element Tree      │
 │ → RenderObject Tree │
 └─────────────────────┘






                         ┌──────────────────────┐
                         │     MaterialApp      │
                         │ (wraps ThemeData)    │
                         └──────────┬───────────┘
                                    │
                         ┌──────────▼───────────┐
                         │        Theme         │
                         │ (colors, fonts, etc.)│
                         └──────────┬───────────┘
                                    │
             ┌──────────────────────┼───────────────────────┐
             │                      │                       │
   ┌─────────▼────────┐   ┌─────────▼──────────┐   ┌────────▼─────────┐
   │  DefaultTextStyle │   │  IconTheme         │   │ MediaQuery       │
   │ (applies to Text) │   │ (applies to Icons) │   │ (device styling) │
   └─────────┬────────┘   └─────────┬──────────┘   └────────┬─────────┘
             │                      │                        │
   ┌─────────▼────────┐   ┌─────────▼─────────┐     ┌────────▼────────┐
   │ Text widget       │   │ Icon widget       │     │ Padding, Layout │
   │ uses style chain  │   │ uses color, size  │     │ adapt to screen │
   └─────────┬────────┘   └─────────┬─────────┘     └─────────────────┘
             │                      │
   ┌─────────▼────────┐   ┌─────────▼─────────┐
   │ Explicit style    │   │ Explicit style    │
   │ (overrides theme) │   │ (overrides theme) │
   └───────────────────┘   └───────────────────┘
