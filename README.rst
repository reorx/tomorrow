Tomorrow
========

A new task scheduler, aimed at quick, clean, and clear.

Concept
-------

The whole program contains three command: ``tomorrow``, ``today``, and ``t``.

The concept of this program is that you should clearly depart you current todo list
and what you planed to do or want to remind tomorrow. You should focus on the former,
and when there's something jumping in your mind, the best way to handle is tag it
*tomorrow*, then go back to work, not let the thought fly away if it is really belongs
to tomorrow, if it isn't the most important thing right now, though it is always
charming to think into the inspiration. So comes this little program, to force us be concentrated, be still, to make the most effecient of our working time. There should always be only two days in our life, **today** and **tomorrow**, there's no "the day after tomorrow".

What is noticeable is that you can only type out what you plan to do for tomorrow, move or copy one task item to tomorrow is not allowed. This may help if we get lazy and keeping delay tasks again and again.

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

    ``t -d`` and ``t $number $another_number`` works the same as ``tomorrow`` does.

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

- select whether to show project name in shell prompt or in output.

- option to show complete list of project - tasks

