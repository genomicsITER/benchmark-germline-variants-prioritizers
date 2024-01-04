 <a name="Variants-prioritizers"></a> 
 
<!-- ------------------ HEADER ------------------ -->
<!-- Developed and maintained by Genomics Division
<!-- of the Institute of Technology an Renewable Energy (ITER)
<!-- Tenerife, Canary Islands, SPAIN
<!-- See the "Contact us" section to collaborate with us to growth
<!-- this repository. ;=)

<!-- ------------------ SECTION 1 ------------------ -->
<p align="left">
  <a href="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers" title="Instituto Tecnológico y de Energ&iacute;as Renovables (ITER) / Institute of Technology and Renewable Energy (ITER)">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/ITER_logo.png" width="auto" /> 
      </a>
</p>

## Benchmarking of causal germline variant prioritizers

<hr>
<!-- ------------------ SECTION 2 ------------------ -->

## Table of contents
<ul>
  <li><a href="#Benchmark-germline-variants-prioritizers">Benchmarking of causal germline variant prioritizers</a></li>
  <li><a href="#First-benchmark-2022">First benchmarking of prioritizers (2022)</a></li>
  <li><a href="#Further-benchmark-2023">Further benchmarking of prioritizers (June 2023)</a></li>
  <li><a href="#References">References</a></li>
  <li><a href="#Acknowledgements">Acknowledgements</a></li>
  <li><a href="#License and Attribution">License and Attribution</a></li>
  <li><a href="#Participating">Participating</a></li>
  <li><a href="#How-to-cite">How to cite this work</a></li>
  <li><a href="#Update logs">Update logs</a></li>
 </ul>

<hr>
<!-- ------------------ SECTION 3 ------------------ -->

<a name="Benchmark-germline-variants-prioritizers"></a>

# Background and justification

Next-generation sequencing facilitates fast and efficient clinical diagnosis of genetic diseases. Whole-exome sequencing (WES) has become a standard approach to efficiently analyze virtually all coding regions from known genes, where more than 80% of pathogenic and known causal variants of Mendelian diseases have been located by now. Since most causal variants of Mendelian diseases are exonic, WES has become a standard diagnostic standard for many practitioners, but causative variant prioritization constitutes a bottleneck. Due to the large number of detectable genetic variants, the development of a standardized protocol to accelerate causative variant identification is necessary.

This repository has been devised to centralize our continuous efforts to benchmark the different public tools that become available for **germline variant prioritization from whole-exome sequencing** data. Partial results of this benchmark, along with an evaluation of our pipeline to conduct WES was published elsewhere [<a href="#References">1</a>].

Our aim is to maintain active this comparison using the same WES dataset while additional tools for variant prioritization become available. As such, this page will be displaying updated results beyond those published in research articles.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 4 ------------------ -->

<a name="First-benchmark-2022"></a>
## First benchmarking of prioritizers (2022)

For this study we aimed to evaluate the performance of open-source tools to accelerate the process of prioritization [<a href="#References">1</a>]. We assessed an in‐house sample‐to‐sequence pipeline and benchmarked freely available prioritization tools for germline causal variants from WES data.

The WES dataset was obtained from 61 unselected patients diagnosed with different diseases and with known genetic disease causes (Table 1). 

<p align="center">
  <a href="#Table1" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/table1.png" width="auto" />
  </a>
</p>

The corresponding Human Phenotype Ontology terms for each case, which would be needed for particular prioritizers, is available from this repository [link]. Libraries were prepared using the DNA Prep with Enrichment kit (Illumina Inc.) following the methods described elsewhere [<a href="#References">2</a>]. A fraction of the causal variants were not captured by WES (8.2%) or did not pass the quality control criteria (13.1%). Worth noting, many of the applications found in the literature were unavailable or had technical limitations. We end up using 9 prioritizers in the evaluation. Variant prioritizations were performed on the WES dataset of 61 patients by the selected tools and recorded to obtain a diagnostic yield when the known causal variant was present in the first, fifth, and 10th top rankings (Figure 1). 

<p align="center">
  <a href="#Figure1" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/figure1.png" width="auto" />
  </a>
</p>

**Figure 1**. Cumulative percentage of correctly prioritized causal variants among the 61 patients with WES data according to evaluated in 2022.
Exomiser performed best in the top first rankings, while LIRICAL led in the top fifth. We concluded that Xrare, Exomiser, LIRICAL, and PhenIX were the most efficient options for variant prioritization.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 5 ------------------ -->

<a name="further-benchmark-2023"></a>

## Further benchmarking of prioritizers (June 2023)

Further benchmarking of prioritizers (June 2023)

We have now added Franklin [link to further details] to this benchmark. As indicated above, prioritization was performed on the WES dataset of 61 patients and the results were recorded to obtain a diagnostic yield when the known causal variant was present in the first, fifth, and 10th top rankings (Figure 2).

<p align="center">
  <a href="#Figure1" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/figure2.png" width="auto" />
  </a>
</p>

**Figure 2**. Cumulative percentage of correctly prioritized causal variants among the 61 patients with WES data according to evaluated tools to date (June 2023).

Exomiser continues to be the best-performing tool in the top first rankings. Franklin rankings were nearly as good as LIRICAL and PhenIX. As an important benefit, Franklin offers other user-friendly representations of the results.

Table 2

Table: Counts and relative frequencies of correctly prioritized causal variants among the 61 patients. Significance for the pairwise comparisons for the percentage of correctly prioritized causal variants between a given tool and Exomiser are indicated.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 6 ------------------ -->

<a name="References"></a>
## References

1: Tosco-Herrera E, Muñoz-Barrera A, Jáspez D, Rubio-Rodríguez LA, Mendoza-Alvarez A, Rodriguez-Perez H, Jou J, Iñigo-Campos A, Corrales A, Ciuffreda L, Martinez-Bugallo F, Prieto-Morin C, García-Olivares V, González-Montelongo R, Lorenzo-Salazar JM, Marcelino-Rodriguez I, Flores C. Evaluation of a whole-exome sequencing pipeline and benchmarking of causal germline variant prioritizers. <i>Hum Mutat.</i> 2022 Dec;43(12):2010-2020. doi: <a href="https://doi.org/10.1002/humu.24459">10.1002/humu.24459</a>. Epub 2022 Sep 12. PMID: <a href="https://pubmed.ncbi.nlm.nih.gov/36054330/">36054330</a>.

2: Díaz-de Usera A, Lorenzo-Salazar JM, Rubio-Rodríguez LA, Muñoz-Barrera A, Guillen-Guio B, Marcelino-Rodríguez I, García-Olivares V, Mendoza-Alvarez A, Corrales A, Íñigo-Campos A, González-Montelongo R, Flores C. Evaluation of Whole-Exome Enrichment Solutions: Lessons from the High-End of the Short-Read Sequencing Scale. <i>J Clin Med.</i> 2020 Nov 13;9(11):3656. <a href="https://doi.org/10.3390/jcm9113656">doi: 10.3390/jcm9113656</a>. PMID: <a href="https://pubmed.ncbi.nlm.nih.gov/33202991/">33202991</a>.
  
<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 7 ------------------ -->

<a name="Acknowledgements"></a>
## Acknowledgements

Analyses were conducted in the TeideHPC thanks to INP-2011-0063-PCT-430000-ACT (INNPLANTA program) from the Spanish Ministry of Economy and Competitiveness. The authors would like to thank the TeideHPC team for the HPC support.

We would also like to thank the authors of Xrare for sharing a copy of the software for benchmark study referenced in [<a href="#References">1</a>].

This work was supported by Instituto de Salud Carlos III (FI18/00230; CD19/00231; PI20/00876) and Ministerio de Ciencia e Innovación [RTC‐2017‐6471‐1], co‐funded by the European Regional Development Fund (ERDF); Cabildo Insular de Tenerife [CGIEU0000219140]; the agreement with Instituto Tecnológico y de Energías Renovables (ITER) to strengthen scientific and technological education, training research, development and innovation in Genomics, Personalized Medicine and Biotechnology [grant number OA17/008]. Alejandro Mendoza‐Alvarez and Eva Tosco‐Herrera were supported by a fellowship from Agencia Canaria de Investigación Innovación y Sociedad de la Información del Gobierno De Canarias (TESIS2020010002, TE-SIS2021010046) co‐funded by European Social Fund.

The funders had no role in the study design, collection, analysis, and interpretation of data, in the writing of the manuscript or in the decision to submit the manuscripts for publication.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 8 ------------------ -->

<a name="License and Attribution"></a>
## License and Attribution

This repository and data exports are released under the CC BY 4.0 license. Please acknowledge the authors and the open source software used in this work (third-party copyrights and licenses may apply).

Please cite this repository as: _"Repository for Benchmarking of causal germline variant prioritizers (accessed on YYYY-MM-DD)"_. And do not forget to <a href="#How-to-cite">cite the papers</a> (see the section "How to cite" below). 

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 9 ------------------ -->

<a name="Participating"></a>
## Participating

> Want to share your relevant links? Place a Direct Message to @labcflores on X (see below).

 <p align="left">
  <a href="https://www.iter.es/areas/area-genomica/" title="Contact us at the Genomics Division of the Institute of Technology and Renewable Energy (ITER), Tenerife, Canary Islands, Spain">
    <img src="https://github.com/genomicsITER/influenza/blob/main/images/ITER_logo.png" width="30%" /> 
  </a>
</p>

Follow us on Twitter <a href="https://twitter.com/labcflores" title="Follow to @labcflores on Twitter" > @labcflores<img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/X_logo-black.png" width="32px" /></a>

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 10 ------------------ -->

<a name="How-to-cite"></a>

## How to cite this work

> Please, see the references with published papers by our group. In addition, please, follow the 'License and Attribution' section to cite this repository.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 11 ------------------ -->

<a name="Update logs"></a>
## Update logs

> January xx, 2024. This repository became fully public. Enjoy the reading! ;=)

> January 4, 2024. Created the private version of this repository.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>
