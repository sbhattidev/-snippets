//////////// Stateless Widget /////////////

class XyzNameStateless extends StatelessWidget {
  const XyzNameStateless({super.key});

  @override
  Widget build(BuildContext context) {
    return const Text("Sameer Bhatti");
  }
}

//////////// Stateful Widget /////////////

class XyzNameStateful extends StatefulWidget {
  const XyzNameStateful({super.key});

  @override
  State<XyzNameStateful> createState() => _XyzNameStatefulState();
}

class _XyzNameStatefulState extends State<XyzNameStateful> {
  @override
  Widget build(BuildContext context) {
    return const Text("Sameer Bhatti");
  }
}
    