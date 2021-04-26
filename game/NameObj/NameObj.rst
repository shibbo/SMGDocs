NameObj
*********

The NameObj class is a class that every Actor in the game must inherit. It implements the basic functionality of an object.

.. cpp:class:: NameObj

.. cpp:function:: NameObj::NameObj(const char *pName)

    :param const char* pName: The name of the NameObj.

.. cpp:function:: virtual ~NameObj()

Destructor for NameObj.

.. cpp:function:: virtual void init(const JMapInfoIter &rJMapInfo)

    :param const JMapInfoIter &rJMapInfo: The JMap information from the NameObj's BCSV entry.

Initialization function. All of the JMap information from the BCSV entry can be read here and stored into the class as needed.

.. cpp:function:: virtual void initAfterPlacement()

.. cpp:function:: virtual void movement()

A function that controls a NameObj's movement. Can be used for changing nerves. Ran every frame.

.. cpp:function:: virtual void draw() const

A function that controls a NameObj's drawing.

.. cpp:function:: virtual void calcAnim()

.. cpp:function:: virtual void calcViewAndEntry()

.. cpp:function:: void initWithoutIter()

Initialize the NameObj with no BCSV entry. It will construct a JMapInfoIter reference and pass it to :cpp:func:`NameObj::init`.

.. cpp:function:: void setName(const char *pName)

    :param const char* &pName: The name of the NameObj.

Assigns the parameter to :cpp:member:`NameObj::mName`.

.. cpp:function:: void executeMovement()

Executes :cpp:func:`NameObj::movement()` if :cpp:member:`mFlags` & 0x2 is 0.

.. cpp:function:: void requestSuspend()

.. cpp:function:: void requestResume()

.. cpp:function:: void syncWithFlags()

.. cpp:member:: const char* mName

The name of the NameObj. This is used to reference a specific NameObj.

.. cpp:member:: u16 mFlags

Flags that change how the NameObj is executed.

- mFlags & 0x1 -- Controls if the NameObj executes its :cpp:func:`NameObj::movement` function. If set to 1, the function will not be executed.
- mFlags & 0x2 -- Unknown, related to :cpp:func:`NameObj::requestResume`.
- mFlags & 0x4 -- Unknown, related to :cpp:func:`NameObj::requestSuspend`.

.. cpp:member:: s16 _A

Unknown purpose.


