Pertinacious
============

* *Warning:* Pertinacious is still under development. Feel free to fork for
fun or to help out, but don't go expecting to use it!

In ruby, as with most programming languages, objects are ephemeral. You
create them, and next time you go looking for them, they could very well be
gone. Not so with Pertinacious objects.

When you mix Pertinacious into a Ruby class of yours, your class is persisted.
You can create, save, delete, and search for instances of your class, even
between 'runnings' of your application or script.

Philosophy
----------

While working on [RDie][], I needed a way to persist instances of pure Ruby
classes written by any system designer. I'm going to try to separate that
concept, that functionality, into a library useful to others.

While considering the topic, I ran into/over a few basic facts about the way
Ruby handles 'data' in an instance of a class:

 * 'Attributes' of a class are stored in instance variables
 * You can't hook directly into instance variable creation (or reading) within
   standard Ruby
 * Most people use attr_accessor and it's attr_* siblings to define attributes
 * You can hook into attr_accessor, and thus, the methods it creates

Due to these findings, I plan to go about achieving the goals of Pertinacious
by [duck punching][dp] attr_* on 'models' that inherit from Pertinacious. The
resultant accessor methods will then be forced to maintain persistence by way
of whatever backend one chooses to plugin to Pertinacious (starting with Soup
and StrokeDB - traditional RBDMS aren't really suited to this application in
the least).

  [RDie]: <http://rubydie.com>
  [dp]: <http://en.wikipedia.org/wiki/Duck_punching>

Getting
-------

When ready, Pertinacious will be available as a gem via `gem install
pertinacious`. However, it is not so (as of yet).

The authoritative source for this project is available at
<http://github.com/elliottcable/pertinacious>. You can clone your own copy with the
following command:

    git clone git://github.com/elliottcable/pertinacious.git

If you want to make changes to the codebase, you need to fork your own github
repository for said changes. Send a pullrequest to [elliottcable][github-elliottcable]
when you've got something ready for the master that you think should be
integrated into the root source.

Bugs or feature requests can be submitted by forking a repository as
previously described, and then using [Ditz][] to add an issue.

  [github-elliottcable]: <http://github.com/elliottcable> (elliottcable on GitHub)

Requirements
------------

To run Pertinacious, you need the following gems:

* *unknown as of yet*

To develop and contribute to Pertinacious, you also need:

* rspec
* rake
* rcov
* ditz
* yard