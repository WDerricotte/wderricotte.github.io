---
layout: page
permalink: /publications/
title: 
pubs:
    - title:   "Intramolecular Proton Transfer in the Isomerization of Hydroxyacetone: A Detailed Characterization Based on Reaction Force Analysis and the Bond Fragility Spectrum"
      author:  "H. Joseph and W. Derricotte"
      journal: "International Journal of Quantum Chemistry"
      year:    "2020"
      url:     "https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.26269"

    - title:   "Symmetry-Adapted Perturbation Theory Decomposition of the Reaction Force: Insights into Substituent Effects Involved in Hemiacetal Formation Mechanisms"
      author:  "W. Derricotte"
      journal: "The Journal of Physical Chemistry A"
      year:    "2019"
      url:     "https://pubs.acs.org/doi/10.1021/acs.jpca.9b06865"

    - title:   "Mapping the 3D Orientation of Piconewton Integrin Traction Forces"
      author:  "J. Brockman, A. Blanchard, V. Ma, W. Derricotte, Y. Zhang, W. Lam, F. Evangelista, K. Salaita, A. Mattheyses"
      journal: "Nature Methods"
      year:    "2018"
      url:     "https://www.nature.com/articles/nmeth.4536"

    - title:   "Localized Intrinsic Valence Virtual Orbitals for the Automated Interpretation of Core Excited States"
      author:  "W. Derricotte and F. Evangelista"
      journal: "The Journal of Chemical Theory and Computation"
      year:    "2017"
      url:     "https://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b00493"

    - title:   "Development and Applications of Orthogonality Constrained Density Functional Theory for the Accurate Simulation of X-Ray Absorption Spectroscopy"
      author:  "W. Derricotte"
      journal: "PhD Thesis Emory University"
      year:    "2017"
      url:     "https://etd.library.emory.edu/concern/etds/fj236288r?locale=en"

    - title:   "Predicting Near Edge X-ray Absorption Spectra with the Spin-Free Exact-Two-Component Hamiltonian and Orthogonality Constrained Density Functional Theory."
      author:  "P. Verma, W. Derricotte, F. Evangelista"
      journal: "The Journal of Chemical Theory and Computation"
      year:    "2016"
      url:     "https://pubs.acs.org/doi/abs/10.1021/acs.jctc.5b00817"

    - title:   "Simulation of X-Ray Absorption Spectra with Orthogonality Constrained Density Functional Theory."
      author:  "W. Derricotte and F. Evangelista"
      journal: "Physical Chemistry Chemical Physics"
      year:    "2015"
      url:     "https://pubs.rsc.org/en/content/articlelanding/2015/CP/C4CP05509H#!divAbstract"

---

{% assign thumbnail="left" %}

{% for pub in page.pubs %}
{% if pub.image %}
{% include image.html url=pub.image caption="" height="100px" align=thumbnail %}
{% endif %}
[**{{pub.title}}**]({% if pub.internal %}{{pub.url | prepend: site.baseurl}}{% else %}{{pub.url}}{% endif %})<br />
{{pub.author}}<br />
*{{pub.journal}}*
{% if pub.note %} *({{pub.note}})*
{% endif %} *{{pub.year}}* {% if pub.doi %}[[doi]({{pub.doi}})]{% endif %}
{% if pub.media %}<br />Media: {% for article in pub.media %}[[{{article.name}}]({{article.url}})]{% endfor %}{% endif %}

{% endfor %}
