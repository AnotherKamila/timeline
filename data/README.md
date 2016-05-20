Data format
===========

What we have here is a collection of several *completely independent* YAML documents, with one document per file. Things that have nothing to do with each other belong in separate documents. Events may be referenced within one document, but not across documents.

Each document must be a map of `event_id: data object`. The following data fields
exist:

- `title`: self-explanatory
- `when`: time specification
- `hierarchy`: When to show this -- see below.
- `short-description`: simple, *completely non-technical* short description that does not require any context whatsoever to understand.
- `good-description`: An extended, informative description.

The descriptions may contain Markdown.

Check out the existing files for examples.

## Hierarchy

The viewing hierarchy determines whether to show a particular event. It is something like a `filesystem path`. Every event specifies a list of hierarchies where it belongs.

When displaying the timeline, you set the target hierarchy -- such as `/cosmology/intro` -- and the timeline will select only events belonging in a hierarchy with a common prefix -- such as `/`, `/cosmology` and `/cosmology/intro`, but not `/history` or `/cosmology/first3minutes`.

The hierarchy also determines which description to pick: the extended description will be shown only if the event's hierarchy exactly matches the target hierarchy on the view. (Note that due to this it makes sense to specify a list of hierarchies where one is a prefix of another.)

## Time specification

may be any of:

- YYYY-MM-DD date, with the usual interpretation
- array with two time specification elements, or object with fields `start` and `end`, to specify an interval. The elements inside may not be intervals.
- object containing `offset_from` and `delta`, where
  - `offset_from` is either `0` (for time since the Big Bang) or an event ID *in the same file*
  - `delta` is a time specification (it may be an interval)
- floating-point number: offset in seconds; `offset_from` must be specificed somewhere

Semantic restrictions
=====================

All information, including the short descriptions, must be accurate. No exceptions. If something is too complicated to be explained, say so, but never simplify to the point of saying something untrue.

TODO
====

- would a "see also" thing be useful? how exactly?
