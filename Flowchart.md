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
   │   AppBar  │              │    Body    │              │ BottomNavBar    │
   └───────────┘              └─────┬──────┘              └────────────────┘
                                     │
                            ┌────────▼─────────┐
                            │   Layout Widgets │
                            └────────┬─────────┘
             ┌───────────────────────┼───────────────────────┐
             │                       │                       │
     ┌───────▼───────┐       ┌───────▼───────┐       ┌───────▼───────┐
     │   Column      │       │     Row       │       │    Stack       │
     └───────┬───────┘       └───────┬───────┘       └───────┬───────┘
             │                       │                       │
   ┌─────────▼────────┐     ┌────────▼────────┐     ┌────────▼────────┐
   │ Child Widgets     │     │ Child Widgets   │     │ Positioned, etc │
   └─────────┬────────┘     └─────────┬────────┘     └─────────────────┘
             │                       │
   ┌─────────▼────────┐     ┌────────▼────────┐
   │ UI Widgets        │     │ Interactive     │
   └─────────┬────────┘     └─────────┬────────┘
             │                       │
   ┌─────────▼──────────┐   ┌────────▼──────────┐
   │ Text, Icon, Image   │   │ ElevatedButton    │
   │ Container, Card     │   │ GestureDetector   │
   │ ListView, GridView  │   │ InkWell, Switch   │
   └─────────────────────┘   └──────────────────┘


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
