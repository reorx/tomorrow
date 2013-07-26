Tomorrow
========

A new task scheduler, aimed at quick, clean, and clear.

Concept
-------

The whole program contains three commands: ``tomorrow``, ``today``, and ``t``.

The concept of this program is that you should clearly distinguish you current todo list
with what you planed to do or want to remind tomorrow. You should focus on the former,
and when something jump into your mind, the best way to handle it is to tag it
*tomorrow*, then go back to work, not let the thought fly away(it is always
charming to think into the inspiration), if it isn't the most important thing
right now, . So comes this little program, to force us be concentrated, be still,
to make the most effecient of our working time.  There should always be only two
days in our life, **today** and **tomorrow**, there's no *"the day after tomorrow"*.

What noticeable is that you can only type out what you plan to do for tomorrow,
move or copy task items to tomorrow is not allowed. This constrains us to be serious
when we get lazy and keep delaying tasks again and again.

Usage
-----

The development of this program is not started yet, below is how I think it should be used:


tomorrow
::::::::

::

    $ cd workspace/project_one

    $ tomorrow
    this is not a project folder, type tomorrow -p $project_name to mark it as a project

    $ tomorrow -p "project one"
    folder /home/reorx/workspace/project_one is marked as project "project one",
    all folers under it will be considered part of the project.

    $ tomorrow
    you havn't planed anything to do for tomorrow, type tomorrow "sth",
    or tomorrow -a to add

    # Add
    $ tomorrow "do sth a"
    [project one] here is what you planed for tomorrow:
    1. do sth a

    $ tomorrow -a
    [project one] type the plan: do sth b

    [project one] here is what you planed for tomorrow:
    1. do sth a
    2. do sth b

    # Swap
    $ tomorrow 2 1
    [project one] Swap 2 and 1, here is what you planed for tomorrow:
    1. do sth b
    2. do sth a

    # Delete
    $ tomorrow -d 1
    [project one] Delete 1, here is what you planed for tomorrow:
    1. do sth a


today
:::::

::

    $ cd workspace/project_one/subfolder

    $ today
    [project one] yesterday you planed:
    1. do sth a

    $ today -h
    what you planed for today yesterday are read-only, you can not change
    or delete them, they'll be archived in the database file.


t
:

::

    $ cd workspace/project_one

    $ t
    [project one] no tasks, type t "sth", or t -a to add

    # Add
    $ t "task a"
    [project one] tasks:
    1. task a

    $ t -a
    [project one] type the task: do sth b

    [project one] tasks:
    1. task a
    2. task b

..

    ``t -d`` and ``t $number $another_number`` work the same as ``tomorrow`` does.

..

::

    # Done
    $ t 1
    [project one] task "task a" is done, 1 task remains:
    1. task b

    # List
    $ t -l
    [project one] all tasks:

    todo:
    1. task b

    done:
    * task a


Ideas
-----

- Select whether to show project name in shell prompt or in output.

- option to show complete list of project - tasks

