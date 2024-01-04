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
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/logos_ITER-FIISC.png" width="auto" /> 
      </a>
</p>

<!-- ------------------ SECTION 2 ------------------ -->

<a name="Benchmark-germline-variants-prioritizers"></a>

# Benchmarking of causal germline variant prioritizers

## Background and justification

Next-generation sequencing facilitates fast and efficient clinical diagnosis of genetic diseases. Whole-exome sequencing (WES) has become a standard approach to efficiently analyze virtually all coding regions from known genes, where more than 80% of pathogenic and known causal variants of Mendelian diseases have been located by now. Since most causal variants of Mendelian diseases are exonic, WES has become a standard diagnostic standard for many practitioners, but causative variant prioritization constitutes a bottleneck. Due to the large number of detectable genetic variants, the development of a standardized protocol to accelerate causative variant identification is necessary.

This repository has been devised to centralize our continuous efforts to benchmark the different public tools that become available for **germline variant prioritization from whole-exome sequencing** data. Partial results of this benchmark, along with an evaluation of our pipeline to conduct WES was published elsewhere [<a href="#References">1</a>].

Our aim is to maintain active this comparison using the same WES dataset while additional tools for variant prioritization become available. As such, this page will be displaying updated results beyond those published in research articles.

<hr>

## Table of contents
<ul>
  <li><a href="#Benchmark-germline-variants-prioritizers">Benchmarking of causal germline variant prioritizers</a></li>
  <li><a href="#First-benchmark-2022">First benchmarking of prioritizers (2022)</a></li>
  <li><a href="#Further-benchmark-2023">Further benchmarking of prioritizers: the case of Franklin (June 2023)</a></li>
  <li><a href="#Software">Bioinformatic tools</a></li>
  <li><a href="#References">References</a></li>
  <li><a href="#Acknowledgements">Acknowledgements</a></li>
  <li><a href="#License and Attribution">License and Attribution</a></li>
  <li><a href="#Participating">Participating</a></li>
  <li><a href="#How-to-cite">How to cite this work</a></li>
  <li><a href="#Update logs">Update logs</a></li>
 </ul>
 
<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10 px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 3 ------------------ -->

<a name="First-benchmark-2022"></a>
## First benchmarking of prioritizers (2022)

For this study we aimed to evaluate the performance of open-source tools to accelerate the process of prioritization [<a href="#References">1</a>]. We assessed an in‐house sample‐to‐sequence pipeline and benchmarked freely available prioritization tools for germline causal variants from WES data.

The WES dataset was obtained from 61 unselected patients diagnosed with different diseases and with known genetic disease causes (Table 1). 

<p align="center">
  <a href="#Table1" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/table1.png" width="auto" />
  </a>
</p>

The corresponding Human Phenotype Ontology terms for each case, which would be needed for particular prioritizers, is available from this repository [link]. Libraries were prepared using the DNA Prep with Enrichment kit (Illumina Inc.) following the methods described elsewhere [<a href="#References">2</a>]. A fraction of the causal variants were not captured by WES (8.2%) or did not pass the quality control criteria (13.1%). Worth noting, many of the applications found in the literature were unavailable or had technical limitations. 

We end up using 9 prioritizers in the evaluation. Variant prioritizations were performed on the WES dataset of 61 patients by the selected tools and recorded to obtain a diagnostic yield when the known causal variant was present in the first, fifth, and 10th top rankings (Figure 1). 

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
<!-- ------------------ SECTION 4 ------------------ -->

<a name="further-benchmark-2023"></a>

## Further benchmarking of prioritizers: the case of <i>Franklin</i> (June 2023)

We have now added <a href="https://franklin.genoox.com">Franklin</a> to this benchmark (Figure 2).

Franklin was tested after uploading all 61 cases of our dataset, their compressed VCF files using GRCh37 (hg19) as a genomic reference, and their respective HPO terms. All cases were processed correctly by the tool except for one case, where an error showed and no results were displayed. We suspect that this error might be related to a high number of HPOs (190 HPO terms).

<p align="center">
  <a href="#Figure2" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/figure2.png" width="auto" />
  </a>
</p>

**Figure 2**. Cumulative percentage of correctly prioritized causal variants among the 61 patients with WES data according to evaluated tools to date (June 2023).

The results of Franklin's performance, using the same dataset of cases, according to the position of the causal variant in the corresponding list of prioritized genetic variants, is shown in Table 2.

Exomiser continues to be the best-performing tool in the top first rankings. Franklin rankings were nearly as good as LIRICAL and PhenIX. As an important benefit, Franklin offers other user-friendly representations of the results.

<a href="#Table2" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/table2.png" width="auto" />
  </a>
</p>

**Table 2**. Counts and relative frequencies of correctly prioritized causal variants among the 61 patients. Significance for the pairwise comparisons for the percentage of correctly prioritized causal variants between a given tool and Exomiser are indicated.


In summary, causal genes have been correctly prioritized in 39 cases out of 61 in total in the top position of the results, while only 41 were correctly identified in the top 5 and top 10 of the output. Franklin then becomes the fourth best performing tool considering only top 1 results, after Exomiser, PhenIX, and LIRICAL. It is surprising how the values between the three top considerations of the results stand very close (39, 41, 41), which may suggest a clear pattern in its performance and would not improve much more after input filtering of low-quality variants.

Franklin holds an easy-going, intuitive, and friendly web interface. Accessible from any type of operating system, no additional software is needed to use the tool nor extensive knowledge of bioinformatics. Many options are accessible to filter by phenotypes, a gene panel, HPO terms, etc, and also seem to be extremely useful for deep further individual investigation of each case, especially for professionals in the clinical field. If a WES/WGS approach is selected, the tool also allows the user to specify a virtual gene panel and easily apply it to the variant results. Due to its high level of automatization and consistent maintenance, automatic reanalysis is certainly a robust strength of this tool. Revisiting the case on the website is enough to update the results according to the possibly changing up-to-date ACMG criteria. However, testing the tool is a slightly challenging experience. The website is so optimized for the individual study of clinical cases, that it allows the application of a customized virtual gene panel as the same filter for several cases, but it does not allow the upload of phenopackets with phenotypic information, or even multiple HPO terms at once at the moment, nor the possibility to easily indicate the same HPO terms for more cases in a few clicks. Automatization of the evaluation of this tool is simply not possible, it requires a highly time-consuming amount of manual work and human interaction with the interface, probably because of the high specialization of the interface for professionals in clinics. Also, the tool was developed by a private company and it is currently running on external private servers. The company supplies robust and constant maintenance, but to an opaque pipeline, where parameters are sealed and cannot be modified, as opposed to open-source software, free to change but non-consistently maintained by the community.
Despite its current flaws, Franklin is a promising variant prioritizing tool. It holds the potential to assist in a clinical context of genetic data analysis of affected individuals to identify causal genetic variants of the disease, accelerating a difficult diagnosis and further access to available treatments for genetic conditions.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 5 ------------------ -->

<a name="Software"></a>

## Bioinformatic tools

<details>
<summary>List of bioinformatic tools assessed (click to display; details are provided below):</summary>
<ul>

<li><a href="https://amelie.stanford.edu/">AMELIE v.2.0.6</a>: an encrypted web-interfaced application designed to prioritize causative variants through analysis of hundreds of thousands of scientific articles while integrating the patient’s phenotype (Birgmeier et al., 2020). Besides the variant (VCF) files, HPO terms are mandatory for the analysis. The results are returned in a web browser showing a ranking of most probable causative genes in decreasing order based on the assigned pathogenicity score. Each run must be submitted manually, which complicates batch analysis.</li>

<li><a href="https://www.sanger.ac.uk/tool/exomiser/">Exomiser v.12.1.0</a>: a command-line and web client designed for differential diagnoses of Mendelian diseases and identification of novel associations between genes and diseases leveraging HPO terms (Smedley et al., 2015). Only the VCF files are mandatory, with the option to include HPO terms and a PED file. The configuration must be manually defined by using a YML file per run. We chose to use the command-line version for automation, relying on the default prioritization algorithm (hiPHIVE), VCF files and HPO terms only, while activating all sources for pathogenicity scores (CADD v.1.5, ReMM v.0.3.1) in the YML template for exonic data and v.1909_hg19 and 1909_phenotype for running databases.</li>

<li><a href="https://lirical.readthedocs.io/en/latest/index.html">LIRICAL v.1.3.4</a>: a command-line application that calculates the likelihood ratio of each phenotypic abnormality. It provides an estimated value of the post-test probability of candidate diagnoses and the consistency of each phenotypic abnormality and the genotype with the diagnosis (Robinson et al., 2020). Since genotypic data is optional, YML files or phenopackets (Jacobsen et al., 2022) are eligible as input. In this study, we used VCF files, and YML files were adapted and processed to ease automatization. LIRICAL and Exomiser are profoundly connected because of the required sharing of local libraries for functionality.</li>

<li><a href="https://github.com/pkuerten/phen-gen">Phen-Gen v.1.0</a>: a command-line application that uses a Bayesian framework to explore previous knowledge of phenotype-driven variant analysis (Javed et al., 2014). VCF files, PED files, and HPO terms are mandatory for the analysis. A mock PED file was provided (since all the patients under study were unrelated). The output scores and the annotated variants were further managed using R v.3.6.3 and RStudio v.1.2.5033 to merge and convert the results into a legible ranking list.</li>

<li><a href="https://github.com/exomiser/Exomiser">PhenIX v.12.1.0</a>: a computational algorithm for filtering and ranking candidate genes based on variant pathogenicity, variant frequency, and potential clinical relevance (Zemojtel et al., 2014). It existed as a standalone tool until it was later integrated into the Exomiser source code. It is currently available as an alternative prioritization algorithm in the configuration of Exomiser (Kelly et al., 2022; Smedley et al., 2015). In this study, we kept the rest of the configuration under default conditions except that the PhenIX algorithm was activated.</li>

<li><a href="https://github.com/a-xavier/tapes">TAPES v.0.1.1</a>: a command-line tool for annotation and variant prioritization according to pathogenetic scores by assigning the American College of Medical Genetics and Genomics criteria for genetic variant interpretation (Richards et al., 2015), ANNOVAR annotations, and implementation models to calculate a unique pathogenicity score (Tavtigian et al., 2018; Xavier et al., 2019). Since HPO terms are not used by this method, annotated VCF files were the only mandatory files for its use. Postfiltered VCF files were used as input.</li>

<li><a href="http://www.mulinlab.org/varnote/application.html#PAT">VarNote-PAT v.2020</a>: a web application designed to prioritize pathogenic regulatory variants using genomic data (Huang et al., 2020). VCF files and PED files are required. Postfiltered VCF files were provided, along with a mock PED file (since all the patients under study were unrelated). All variants were selected on the settings page to be included in the results report.</li>

<li><a href="https://web.stanford.edu/group/wonglab/Xrare/xrare-pub.2021.html">Xrare v.2021</a>: an R-dependent library dedicated to disease-causing variant prioritization based on phenotypes and genetic features. The algorithm annotates each variant internally with a specific format in order to assign “predicted” phenotype similarity scores following ACMG/AMP best practices in assessing pathogenicity of genetic variants. It requires a compressed VCF file and HPO terms per sample (Li et al., 2019).</li>

<li><a href="https://franklin.genoox.com">Franklin</a>:Franklin is an online tool, defined as a connectivity hub across the medical genetics domain to extend actionable genomic information to  patients care.</li>

<ul>
</details>


<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 6 ------------------ -->

<a name="References"></a>
## References

1: Tosco-Herrera E, Muñoz-Barrera A, Jáspez D, Rubio-Rodríguez LA, Mendoza-Alvarez A, Rodriguez-Perez H, Jou J, Iñigo-Campos A, Corrales A, Ciuffreda L, Martinez-Bugallo F, Prieto-Morin C, García-Olivares V, González-Montelongo R, Lorenzo-Salazar JM, Marcelino-Rodriguez I, Flores C. **Evaluation of a whole-exome sequencing pipeline and benchmarking of causal germline variant prioritizers**. <i>Hum Mutat.</i> 2022 Dec;43(12):2010-2020. doi: <a href="https://doi.org/10.1002/humu.24459">10.1002/humu.24459</a>. Epub 2022 Sep 12. PMID: <a href="https://pubmed.ncbi.nlm.nih.gov/36054330/">36054330</a>.

2: Díaz-de Usera A, Lorenzo-Salazar JM, Rubio-Rodríguez LA, Muñoz-Barrera A, Guillen-Guio B, Marcelino-Rodríguez I, García-Olivares V, Mendoza-Alvarez A, Corrales A, Íñigo-Campos A, González-Montelongo R, Flores C. **Evaluation of Whole-Exome Enrichment Solutions: Lessons from the High-End of the Short-Read Sequencing Scale**. <i>J Clin Med.</i> 2020 Nov 13;9(11):3656. <a href="https://doi.org/10.3390/jcm9113656">doi: 10.3390/jcm9113656</a>. PMID: <a href="https://pubmed.ncbi.nlm.nih.gov/33202991/">33202991</a>.
  
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

This work was supported by Instituto de Salud Carlos III (FI18/00230; CD19/00231; PI20/00876) and Ministerio de Ciencia e Innovación [RTC‐2017‐6471‐1], co‐funded by the European Regional Development Fund (ERDF); Cabildo Insular de Tenerife [CGIEU0000219140]; the agreement with Instituto Tecnológico y de Energías Renovables (ITER) to strengthen scientific and technological education, training research, development and innovation in Genomics, Personalized Medicine and Biotechnology [grant number OA17/008]. Alejandro Mendoza‐Alvarez and Eva Tosco‐Herrera were supported by a fellowship from Agencia Canaria de Investigación Innovación y Sociedad de la Información del Gobierno De Canarias (TESIS2020010002, TESIS2021010046) co‐funded by European Social Fund.

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
