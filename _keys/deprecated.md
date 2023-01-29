---
name: Deprecated
key: deprecated
type: Boolean
group: sub-stacks
description: Hide (really really) this stack in the Library
available: 7
---


When this value is true this Stack will not appear by default in the Stacks Library. Even when the user chooses Show Hidden this stack will remain invisible.

Child stacks used with AddTypes often have no use outside of their parent stack. To reduce clutter and make things simpler for the user you can hide a stack.

> Note:  Users cannot choose to show deprecated stacks.  Showing hidden stacks is useful for when you have hidden something but the user might need the stack in a very rare circumstance.  If you want the stack to sometimes be visible, you should use [Hidden](../hidden)
