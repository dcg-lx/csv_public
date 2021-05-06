---
layout: home
title: Convex Solid Voids
---
[Convex and Solid-Voids](http://solidvoids.fa.ulisboa.pt){:target="_blank" rel="noopener"} is a research project developed by the Design Computing Group at the Faculty of Architecture, University of Lisbon.

Convex voids are 3D representations of open urban spaces auto-generated based on the input of surrounding buildings, topography and other urban limits.
They are utilized to measure multiple morphological attributes regarding urban spaces and are aggregated to form Solid-Voids which act as containers for this data.

More information is available in the homepage of the project: [http://solidvoids.fa.ulisboa.pt](http://solidvoids.fa.ulisboa.pt){:target="_blank" rel="noopener"}.

## Tools

The tools consist of two main parts. The first part is a pre-processor that runs either as a standalone command line interface (CLI), or as a QGIS 2 plugin. The second part is a series of Grasshopper algorithms. This site deals only with the first part.

Installation instructions for the original QGIS 2 plugin can be found at the homepage of the project, tutorial section [tutorial](http://solidvoids.fa.ulisboa.pt/tutorial/){:target="_blank" rel="noopener"}.

The standalone CLI is distributed as a Docker image. Installation and usage instructions are available [here]({{site.baseurl}}{% post_url 2021-04-30-cli-instructions %})

A QGIS 3 plugin is currently under development and will be released here when ready.

## Getting started

Your first port of call should be the QGIS 2 plugin and applicable tutorial in the project [homepage](http://solidvoids.fa.ulisboa.pt){:target="_blank" rel="noopener"}.

The Docker CLI is not yet sufficiently tested but has the advantage of being completely contained, requiring no external dependency installations.

If you are experiencing problems, or want to experiment with new developments such as the CLI interface or QGIS 3 plugin, you can get started here:

- CLI installation and [instructions]({{site.baseurl}}{% post_url 2021-04-30-cli-instructions %})
- CLI help [documentation]({{site.baseurl}}{% post_url 2021-05-03-cli-help %})
- QGIS 3 installation and instructions (under development)
- Check open and closed [issues](https://github.com/joaoponceleao/dcg_uvoids/issues?q=is%3Aissue){:target="_blank" rel="noopener"} for workarounds
- Submit a bug [report](https://github.com/joaoponceleao/dcg_uvoids/issues/new/choose){:target="_blank" rel="noopener"}

## Authors

- Jose Nuno Beirao, Ljiljana Cavic, Andre Chaszar, Elif Ensari, Rui de Klerk, Joao Paulouro, Rusne Sileryte

The project is being developed at the Design Computing Group (DCG) of the Faculty of Architecture, University of Lisbon, currently headed by Jose Nuno Beirao.

See more details on the [team](http://solidvoids.fa.ulisboa.pt/people/){:target="_blank" rel="noopener"} who participated in this project.
