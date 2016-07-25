# Modifications in TinyMCE v4.1.19

This is a fork from https://github.com/tinymce/tinymce/tree/4.1.9

## Issue Description

If TinyMCE is used in "content_editable: true" mode there is no iFrame-container for TineMCE's content so TineMCE can potentially change a content of the page where it is placed. So this actually happens in case of iOs in function tapLinksAndImages that binds custom callback on all click event for all anchors and prevents its propagation. This leads to an issue when all links on the page are unclickable.

## Fix Description

To fix this isDescendant function was added. This function checks whether an element is descendant of an other element. So tapLinksAndImages was modified to apply its logic for elements inside of Editor container element only.
