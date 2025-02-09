# MDAnalysis and Blender

The [Molecular Nodes](https://bradyajohnston.github.io/MolecularNodes/) plugin (by
@BradyAJohnston) for the 3D animation and rendering program
[Blender](https://www.blender.org/) makes it possible to do highly professional renderings
of MD trajectories. Under the hood, *Molecular Nodes* uses MDAnalysis for trajectory I/O.

## Team

@yuxuanzhuang will work with anyone interested in Blender/MDA.
@bradyajohnston will be available remotely to answer questions and work on Blender/MDA.

## Background

Blender is used for a wide variety of 3D modelling and animation tasks throughout the games,
TV, movies and VFX industries. It has become a favourite among many for its speed of
development, wide range of features and that it is 100% free and open source.

Blender comes bundled with it's own python kernel, which enables extremely extensive
scripting possibilities through the quite comprehensive API. This has enabled a variety of
scientific visualisation applications that interface with, or are built on top of Blender.

One such project is Molecular Nodes, which enables efficient import of structural biology
data into Blender for advanced visualisation and rendering capabilities. For the import of
molecular dynamics trajectories, `MDAnalysis` has been used as the interface enabling import
in to Blender.

The current implementations reads all of the requested frames of the trajectory in to
memory, and discards the MDAnalysis session after import is complete.

### A live MDAnalysis session
@yuxuanzhuang already has a [working
prototype](https://github.com/BradyAJohnston/MolecularNodes/pull/287) to maintain a live
MDAnalysis session when importing trajectories, enabling the streaming of trajectories
rather than loading in to memory. This also enables the live viewing of an MDAnalysis
universe or atom group, which can then be altered with additional selections or
transformations, which will be reflected inside of the Blender viewport. This is limited
however to working within the python scripting interface inside of Blender. Blender does
come with a scripting interface but it is lacking some features that users are used to from
more modern IDEs.

### Interacting via Jupyter Notebooks
As Blender contains it's own python kernel, this can be used as a kernel for a Jupyter
Notebook, enabling notebook-style scripting and analysis as users are used to with
MDAnalysis, all connected to a live Blender session which can display the current state of
the analysis or session.

The easiest way to do this currently is via the
[`BNotebooks`](https://github.com/bradyajohnston/BNotebooks) add-on for Blender, which
enables registering Blender as a potential kernel for use in notebooks.

## Project ideas

- Working on an optimal API
  - Much of Blender's API is overly verbose and unintuitive in its usage. Potential for a
    more streamlined API for working with notebooks with structures and trajectories inside
    of Blender.
- Improving the code's performance.
  - Improving performance of importing and updating trajectories inside of Blender
- Creating a prototype to visualize analysis results.
  - While import of atoms and their trajectories is somewhat straightforward, there remains
    a lot of potential for visualisation of specific analyses from MDAnalysis inside of
    Blender that remain unexplored.
- Better timeline management.
  - Improved selection of frames of the trajectory, animation playback, interpolation
    between frames. Related to the API section also.
- Select atoms within Blender (which may require an advanced level of Blender knowledge).
  - Creating atom selections inside of Blender via the GUI, that can be reflected inside of
    the MDAnalysis session and used for further analysis.