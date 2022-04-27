---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "enclone: precision clonotyping and analysis of immune receptors"
authors: [Jaffe DB, Shahi P, Adams BA, Chrisman AM, Finnegan PM, Raman N, Royall AE, Tsai F, Vollbrecht T, Reyes DS, McDonnell WJ]
date: 2022-04-22
doi: "10.1101/2022.04.21.489084"

# Schedule page publish date (NOT publication's date).
publishDate: 2019-06-28T19:06:05-05:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: "enclone: precision clonotyping and analysis of immune receptors"
publication_short: "https://www.biorxiv.org/content/10.1101/2022.04.21.489084v1.full.pdf"

abstract: ""

# Summary. An optional shortened abstract.
summary: "Half a billion years of evolutionary battle forged the vertebrate adaptive immune system, an astonishingly versatile factory for molecules that can adapt to arbitrary attacks. The history of an individual encounter is chronicled within a clonotype: the descendants of a single fully rearranged adaptive immune cell. For B cells, reading this immune history for an individual remains a fundamental challenge of modern immunology. Identification of such clonotypes is a magnificently challenging problem for three reasons:
● The cell history is inferred rather than directly observed: the only available data are the sequences of V(D)J molecules occurring in a sample of cells.
● Each immune receptor is a pair of V(D)J molecules. Identifying these pairs at scale is a technological challenge and cannot be done with perfect accuracy—real samples are mixtures of cells and fragments thereof.
● These molecules can be intensely mutated during the optimization of the response to particular antigens, blurring distinctions between kindred molecules.
It is thus impossible to determine clonotypes exactly. All solutions to this problem make a trade-off between sensitivity and specificity; useful solutions must address actual artifacts found in real data. We present enclone1, a system for computing approximate clonotypes from single cell data,
and demonstrate its use and value with the 10x Genomics Immune Profiling Solution. To test it, we generate data for 1.6 million individual B cells, from four humans, including deliberately enriched memory cells, to tax the algorithm and provide a resource for the community. We analytically determine the specificity of enclone’s clonotyping algorithm, showing that on this dataset the probability of co-clonotyping two unrelated B cells is around 10-9. We prove that using only heavy chains increases the error rate by two orders of magnitude.
enclone comprises a comprehensive toolkit for the analysis and display of immune receptor data. It is ultra-fast, easy to install, has public source code, comes with public data, and is documented at bit.ly/enclone. It has three “flavors” of use: (1) as a command-line tool run from a terminal window, that yields visual output; (2) as a command-line tool that yields parseable output that can be fed to other programs; and (3) as a graphical version (GUI)."

tags: []
categories: []
featured: true

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
url: https://twitter.com/WyattMcDonnell/status/1519086894604111872
icon_pack: fab
icon: twitter

url_pdf: https://www.biorxiv.org/content/10.1101/2022.04.21.489084v1.full.pdf
url_code: https://github.com/10XGenomics/enclone
url_dataset:
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
