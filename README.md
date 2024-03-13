# What is this?
A little program with web UI and search interface to calculate [Bacon's Law](https://en.wikipedia.org/wiki/Six_Degrees_of_Kevin_Bacon) for any given actor, as well as applying the same principle to other actors (not just x-to-Bacon, but also y-to-z).
# Branches
## Main
This is where the program code is located. It mainly consists of a self-programmed Matrix class and code for performing the Dijkstra algorithm on an [adjacency matrix](https://en.wikipedia.org/wiki/Adjacency_matrix).

The adjecency matrix is built from data that stems from an actors.csv, listing one movie per row and all actors starring in that movie. We then extracted that data into a database in order to make it easier to access actor-to-actor relations.
## Website
Here are the files for the web UI. Any user can  use the interface to search for actor names and find their Degree of Bacon, or respectively their relationship to any other actor.
# Complications
The actors.csv was mal-encoded (a case of [Mojibake](https://en.wikipedia.org/wiki/Mojibake)). This has destroyed most European letters.

We managed to revert this by re-encoding and re-decoding the given file, but some broken characters cannot be reverted, such as ü or ä, but also æ, œ, þ, í, ó. The information about them got lost in the original encode process.
As of now, the database has the broken names for chese characters, replaced with a single � symbol instead of the correct character, but some names were already manually corrected, like "Jürgen".
It is not yet decided how to handle this in the user search.
