# Introduction to Systems Programming

An interactive collection of lecture notes that introduce core systems programming topics.
This repository is based on the [_PDC For Beginners_](https://www.learnpdc.org/PDCBeginners/) book.
It's a great guide to parallel computing and you should go check it out if you're interested.

## Information for Contributing Authors

We happily accept contribution of lecture notes, textbook contents, and additional contributions!
Please follow the contribution instructions below!

## Setting up the local authoring environment

This project is served using the [Runestone authoring environment](https://github.com/RunestoneInteractive/rs).

### Requirements

The only software required to get started is Python 3
At the time of writing this, Python 3.11.x was the greatest supported version as 3.12.x removes necessary standard library modules.
Once Python is installed, clone the repository and run the following commands within the repository:

```
pip install -r requirements.txt
```

## Contribution Guide

The first step is to fork this GitHub repository.
Once you've got the repository forked, go ahead and clone it and set up your environment.

Chapter content is added to the `_sources/` directory. For example, if you are
a chapter 0 section author, your section will be located under
`_sources/0-introduction` as a separate .rst file.

### Writing content

_Introduction to Systems Programming_ is written using Runestone components and restructured
text (reST).
The following [cheat sheet](http://openalea.gforge.inria.fr/doc/openalea/doc/_build/html/source/sphinx/rest_syntax.html)
is a useful guide for the different markup components needed to write a document using restructured text.

In addition to restructured text, runestone chapters contain Runestone
Directives (see the
[Runestone Author Guide](https://runestone.academy/runestone/static/authorguide/index.html)
for details).
Runestone Directives allow the integration of many interactive
content, such as videos, multiple choice questions, parson problems, and others.

The following example illustrates how a particular section may be set up using
restructured text and Runestone directives:

```rst
3.x This is a section heading
----------------------------------------

Section content would go here. Notice how the number of hyphens/dashes extends
past the section heading. The number of hyphens must be at least as long as
the section title itself.

Here is an example of **bold** text. Here is an example of *italicized* text.
This (:math:`a^2 + b^2 = c^2`) is an example of an in-lined LaTeX math equation.

The following is an example of a standalone math equation:

.. math::

   \sum_{i=0}^n i \equiv \frac{n \times (n + 1}{2}



3.x.1: This is a subsection heading
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Notice how the carats (^) must be at least as long as the subsection heading
text.

Here is an example of a URL: `CSinParallel <csinparallel.org>`_

Here is how a video may be included (from the Runestone documentation):

.. video:: video-ex1
   :controls:
   :thumb: /_images/whileloop.png

   http://media.interactivepython.org/thinkcsVideos/whileloop.mov

```

### Previewing your work

There are two main commands that an author needs to know to preview
their work locally.

Use the `runestone preview` command to compile your changes locally. Most
warnings can be ignored. If the project does not build for whatever reason,
please open an issue.

Once the project has been built, start a local server using the `runestone serve` command.
The server is typically served at [https://localhost:8000](https://localhost:8000) when running.

### Troubleshooting tips

Here are some helpful tips if you find yourself getting stuck

- If `runestone build` does not work, check your Runestone version. If it
  is 5.6.0 or later, open up `conf.py` and ensure line 21 reads
  `from runestone import runestone_static_dirs, runestone_extensions, setup`
  (notice the addition of `, setup` at the end of the command).

- Make sure that your runestone objects have unique keys. If you reuse keys,
  there will be build errors.

- The video format has to be in `mov` format for Runestone to interpret it.
  Annoying, yes, but a tool like `ffmpeg` can automatically do the conversion
  for you. A command like the following usually works (for `mp4` to `mov`):
  `ffmpeg -i video.mp4 -f mov video.mov`.

## Merging changes back in

This project uses the [fork and pull model](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)
for collaborative development.

When you are ready to share your changes, please create a
[Git Pull Request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).
GitHub also has specific documentation on how to [create a pull request from
a fork](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)

After we review your work, it will be merged into the main branch of the
repository. We will rebuild the book on our server soon after!
