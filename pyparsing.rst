PyParsing
---------

This is just a tokenizer: no structured output.


.. code-block:: python

    command = Or([Literal("before"),  Literal("after")])
    position = Word(nums)
    command_with_position = (command + position)
    patt  = OneOrMore(command_with_position)

    test = "before 1000 after 600 before 8293"
    print patt.parseString(test)

    # ['before', '1000', 'after', '600', 'before', '8293']




Use ``setParseAction`` to get a tree.

.. code-block:: python

    class Node(object):
        pass

    class CWP(Node):
        def __init__(self, toks):
            self.command = toks[0]
            self.position = toks[1]
        def __repr__(self):
            return "CWP(%s,%s)" % (self.command, self.position)

    class Command(Node):
        def __init__(self, toks):
            self.command = toks[0]
        def __repr__(self):
            return "Command(%s)" % (self.command)

    class Pos(Node):
        def __init__(self, toks):
            self.pos = toks[0]
        def __repr__(self):
            return "Pos(%s)" % (self.pos)

    command = Or([Literal("before"),  Literal("after")]).setParseAction(Command)
    position = Word(nums).setParseAction(Pos)
    command_with_position = (command + position).setParseAction(CWP)
    patt  = OneOrMore(command_with_position)

    test = "before 1000 after 600 before 8293"
    print patt.parseString(test)

    # [CWP(Command(before),Pos(1000)), CWP(Command(after),Pos(600)), CWP(Command(before),Pos(8293))]


