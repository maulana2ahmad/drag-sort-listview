DragSortListView
================

This is an extension of the Android ListView that enables
drag-and-drop re-sorting of list items. The code is
based on the TouchInterceptor (link) (TI) from the Google
Music app (link) (silly if it weren't!); therefore,
the essential behavior is the same---list item heights and
visibilities are adjusted to create an empty slot that tracks
the item being dragged. User-provided Listener objects are
informed of drag and drop events.

While using the TI in an app of mine, I noticed the following
behaviors that I thought needed polishing (in order of
importance):

1. Scrolling while dragging is erratic. A scroll is initiated
in the TI only when a MOVE event is detected. I don't think
this is a user-expected behavior.
2. List item View heights must be homogeneous and pre-specified.
3. Shuffling of list items is buggy for some drag movements
(e.g. shuffle occurs only after large overlap of floating View
with visible list items, last/first item in list does not shuffle,
etc.).
4. Dropping the floating View can cause the list to unexpectedly
``scroll.''
5. Region for item drag initiation is hard-coded in the TI.
6. Floating View is not bounded to ListView (maybe not such
an issue, mostly asthetic).

The above shortcomings caused a major reworking of the
TI implementation details, resulting in DragSortListView. I see a
lot of potential in a clean drag-sort list; any app with
a user-created list (e.g. "favorites") should benefit.

1. Scrolling while dragging is now intuitive and easily
customizable.
2. Arbitrary item heights are supported.
3./4. Dragging/Dropping/Drag-scrolling are mostly clean.
5. Drag initiation is customizable at the per-item level.
6. Bounds on floating View (big whoop?)

I hope you find it useful! And please, help me improve the thing!


Installation
------------