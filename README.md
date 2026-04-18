 <a name="Variants-prioritizers"></a> 
 
<!-- ------------------ HEADER ------------------ -->
<!-- Developed and maintained by Genomics Division
<!-- of the Institute of Technology an Renewable Energy (ITER)
<!-- Tenerife, Canary Islands, SPAIN
<!-- See the "Contact us" section to collaborate with us to grow
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
  <li><a href="#Further-benchmark-2023">Further benchmarking of prioritizers: the case of <i>Franklin</i> (June 2023)</a></li>
  <li><a href="#Added-GEBRA-2026">New addition to the benchmarking: <i>GEBRA</i> (April 2026)</a></li>
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

**Figure 1**. Cumulative percentage of correctly prioritized causal variants among the 61 patients with WES data evaluated in 2022.
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

<a name="#Added-GEBRA-2026"></a>

## New addition to the benchmarking: <i>GEBRA™</i> (April 2026)

This addition comes from a collaboration between 3billion, Inc. and this research group in the domain of rare Mendelian disease genomics and gene prioritization. Following the publication of our previous study (Tosco‐Herrera, et al. (2022)), where we evaluated prioritization algorithms using real datasets, 3billion, Inc. grated us access to their proprietary prioritization tool, <a href="https://3billion.io/gebra">GEBRA™</a>, to perform an independent benchmarking. After discussing the objectives and technical considerations, we agreed to include the tool to our benchmark, along with the rest of the 10 previously assessed tools.

Our group was responsible for designing the benchmarking framework, performing the analyses, and interpreting the results. The company, 3billion, Inc. provided access to GEBRA™, continuous technical support, and guidance through its functions.

### Procedure
GEBRA™ was accessed on March 10, 2026 for processing the complete dataset. Minimal required clinical and phenotypic information was provided in bulk using the default spreadsheet template. This step generated individual case accessions in the tool. Each corresponding VCF file (compressed, using GRCh37/hg19 reference and GATK caller) was manually uploaded and revised, directly proceeding with the analyses. The tool supports bulk VCF upload through AWS keys and prior permission of the company, although this function was not used to simplify the workflow and recreate plausible user experience in clinical fields, where few patients are processed but deeply investigated individually.
All cases were analyzed one time per patient dataset, using GEBRA™ with default WES parameters, as «Proband Only Exome» tests and with Secondary Findings activated. When all analyses were completed, the resulting variant rankings were manually reviewed to assess performance and concordance with the available genetic diagnosis. Evaluation was based on whether the causal gene for each diagnosis appeared within the first to tenth positions in the prioritized results.

### Results
GEBRA™ was accessed (date range: March 10-11, 2026) and used to process the available 61 WES data files and added to the benchmark. Sample processing did not rely on local hardware, as all analyses were executed on a remote server. The system fully supports parallel processing, analyzing all samples in under 15 minutes. Table 1 presents the performance of GEBRA™ using the same WES data, following the same procedure as with the earlier tools. GEBRA™ emerged as the new best-performing tool in the rankings (Figure 3). It not only outperformed previously assessed tools, but also features a user-friendly interface. Its design is extremely focused on result exploration for individual patients.

> WIP: Upload and change figure 2 to figure 3 !!!!!!!
<p align="center">
  <a href="#Figure3" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/figure3.tif" width="auto" />
  </a>
</p>

**Figure 3**. Cumulative proportion of correctly prioritized causal variants across the total 61 patients, by all tools evaluated to date, now including GEBRA™ (March 2026).

The correct causal genes were identified in 44 cases out of 61 in the top position (top 1) of the rankings, as shown in Table 3. In the top 5 results, the correct gene was prioritized in 50 cases, with only one additional success when considering the top 10. GEBRA™ now leads the benchmarking in all top rankings, surpassing Exomiser, PhenIX, LIRICAL and Franklin, available from the existing benchmarking. The results (44, 50, 51) are higher but remarkably close to Exomiser (42, 46, 48). This must be framed into the following important information. Exomiser is an open-source tool and did not integrate AI to the prioritization algorithm in the benchmarked version (v.12.1.0). This update suggests that specialized AI-integrated tools like GEBRA™ could enhance performance by a better understanding of each individual’s genomic context.

> WIP: Upload and change table 2 to table 3 !!!!!!!
<a href="#Table3" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/figures/table3.png" width="auto" />
  </a>
</p>

**Table 3**. Counts and relative frequencies of correctly prioritized causal variants among the 61 patients. Significance for the pairwise comparisons for the percentage of correctly prioritized causal variants between a given tool and GEBRA™ (as the best performing tool in this analysis freeze) are indicated.

GEBRA™ offers an intuitive web interface, especially tailored for clinical use. It is accessible from any device, accepts HPO terms as phenotypes, and supports bulk uploads of patients’ clinical information, along with gene panels or custom lists of genes of interest. This makes it highly useful for in-depth investigations. Users receive periodic notifications about credit balances and pricing for FASTQ or VCF runs. Although GEBRA™ is not for free, due to private company support, the tool guarantees consistent updates and native automatic reanalysis, updating the results according to the latest version of databases and available ACMG criteria.
The clinical-focused design of GEBRA™ produced some challenges in the testing process. It supports multiple VCF uploads only via AWS keys after company approval, complicating batch processing. As far as we are concerned, phenopackets are not yet supported; instead, it relies on individual HPO terms, entered manually or via bulk upload (only for clinical data) using a simple template, also showing permanently in the web application and interfering with result exploration later in the analysis, especially for patients with multiple HPOs. Also, automation of this tool is cumbersome, due to its web-based design. It requires a large amount of time and human interaction to test with bigger patient cohorts than usual in clinical practice.
GEBRA™ has been developed by a private company. The source code is unavailable, and its usage involves an economic cost and the use of external servers. The pipeline is visible but not fully detailed, with limited parameter customization, unlike open-source tools. They are free to use and highly customizable, but they often lack consistent technical support. Despite these research-related limitations, GEBRA™ has emerged as a prioritization tool incorporating AI at its specialized core algorithm. It shows strong potential as a valuable clinical assistant, especially for challenging diagnoses, and ensures reproducible genetic pipelines at minimal technical cost, enabling faster detection, diagnosis and treatment.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>



<hr>
<!-- ------------------ SECTION 6 ------------------ -->

<a name="Software"></a>

## Bioinformatic tools

<details>
<summary>List of bioinformatic tools assessed (click to display; details are provided below):</summary>
<ul>

<li><a href="https://amelie.stanford.edu/">AMELIE v.2.0.6</a>: an encrypted web-interfaced application designed to prioritize causative variants through analysis of hundreds of thousands of scientific articles while integrating the patient’s phenotype. Besides the variant (VCF) files, HPO terms are mandatory for the analysis. The results are returned in a web browser showing a ranking of most probable causative genes in decreasing order based on the assigned pathogenicity score. Each run must be submitted manually, which complicates batch analysis.</li>

<li><a href="https://www.sanger.ac.uk/tool/exomiser/">Exomiser v.12.1.0</a>: a command-line and web client designed for differential diagnoses of Mendelian diseases and identification of novel associations between genes and diseases leveraging HPO terms. Only the VCF files are mandatory, with the option to include HPO terms and a PED file. The configuration must be manually defined by using a YML file per run. We chose to use the command-line version for automation, relying on the default prioritization algorithm (hiPHIVE), VCF files and HPO terms only, while activating all sources for pathogenicity scores (CADD v.1.5, ReMM v.0.3.1) in the YML template for exonic data and v.1909_hg19 and 1909_phenotype for running databases.</li>

<li><a href="https://lirical.readthedocs.io/en/latest/index.html">LIRICAL v.1.3.4</a>: a command-line application that calculates the likelihood ratio of each phenotypic abnormality. It provides an estimated value of the post-test probability of candidate diagnoses and the consistency of each phenotypic abnormality and the genotype with the diagnosis. Since genotypic data is optional, YML files or phenopackets are eligible as input. In this study, we used VCF files, and YML files were adapted and processed to ease automatization. LIRICAL and Exomiser are profoundly connected because of the required sharing of local libraries for functionality.</li>

<li><a href="https://github.com/pkuerten/phen-gen">Phen-Gen v.1.0</a>: a command-line application that uses a Bayesian framework to explore previous knowledge of phenotype-driven variant analysis. VCF files, PED files, and HPO terms are mandatory for the analysis. A mock PED file was provided (since all the patients under study were unrelated). The output scores and the annotated variants were further managed using R v.3.6.3 and RStudio v.1.2.5033 to merge and convert the results into a legible ranking list.</li>

<li><a href="https://github.com/exomiser/Exomiser">PhenIX v.12.1.0</a>: a computational algorithm for filtering and ranking candidate genes based on variant pathogenicity, variant frequency, and potential clinical relevance. It existed as a standalone tool until it was later integrated into the Exomiser source code. It is currently available as an alternative prioritization algorithm in the configuration of Exomiser. In this study, we kept the rest of the configuration under default conditions except that the PhenIX algorithm was activated.</li>

<li><a href="https://github.com/a-xavier/tapes">TAPES v.0.1.1</a>: a command-line tool for annotation and variant prioritization according to pathogenetic scores by assigning the American College of Medical Genetics and Genomics criteria for genetic variant interpretation, ANNOVAR annotations, and implementation models to calculate a unique pathogenicity score. Since HPO terms are not used by this method, annotated VCF files were the only mandatory files for its use. Postfiltered VCF files were used as input.</li>

<li><a href="http://www.mulinlab.org/varnote/application.html#PAT">VarNote-PAT v.2020</a>: a web application designed to prioritize pathogenic regulatory variants using genomic data. VCF files and PED files are required. Postfiltered VCF files were provided, along with a mock PED file (since all the patients under study were unrelated). All variants were selected on the settings page to be included in the results report.</li>

<li><a href="https://web.stanford.edu/group/wonglab/Xrare/xrare-pub.2021.html">Xrare v.2021</a>: an R-dependent library dedicated to disease-causing variant prioritization based on phenotypes and genetic features. The algorithm annotates each variant internally with a specific format in order to assign “predicted” phenotype similarity scores following ACMG/AMP best practices in assessing pathogenicity of genetic variants. It requires a compressed VCF file and HPO terms per sample.</li>

<li><a href="https://franklin.genoox.com">Franklin</a>: Franklin is an online tool, defined as a connectivity hub across the medical genetics domain to extend actionable genomic information to  patients care.</li>

<li><a href="https://3billion.io/gebra">GEBRA</a>: A proprietary online tool, innovatively integrating AI in its prioritizing algorithm and designed especially for medical genetic professionals, to provide quick aid in gene and causal prioritization of Mendelian diseases in clinical settings.</li>

<ul>
</details>


<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>

<hr>
<!-- ------------------ SECTION 7 ------------------ -->

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
<!-- ------------------ SECTION 8 ------------------ -->

<a name="Acknowledgements"></a>
## Acknowledgements

Analyses were conducted in the TeideHPC thanks to INP-2011-0063-PCT-430000-ACT (INNPLANTA program) from the Spanish Ministry of Economy and Competitiveness. The authors would like to thank the TeideHPC team for the HPC support.

We would also like to thank the authors of Xrare for sharing a copy of the software for benchmark study, and 3billion, Inc. for granting access to the tool and allowing the publication of these results, along with the rest of the benchmarking. [<a href="#References">1</a>].

This work was supported by Instituto de Salud Carlos III (FI18/00230; CD19/00231; PI20/00876) and Ministerio de Ciencia e Innovación [RTC‐2017‐6471‐1], co‐funded by the European Regional Development Fund (ERDF); Cabildo Insular de Tenerife [CGIEU0000219140]; the agreement with Instituto Tecnológico y de Energías Renovables (ITER) to strengthen scientific and technological education, training research, development and innovation in Genomics, Personalized Medicine and Biotechnology [grant number OA17/008]; and Agencia Canaria de Investigación Innovación y Sociedad de la Información del Gobierno De Canarias (TESIS2020010002, TESIS2021010046) co‐funded by European Social Fund.

The funders had no role in the study design, collection, analysis, and interpretation of data, in the writing of the manuscripts or in the decision to submit the manuscripts for publication.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 9 ------------------ -->

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
<!-- ------------------ SECTION 10 ------------------ -->

<a name="Participating"></a>
## Participating

> Want to share your relevant links? Place a Direct Message to @labcflores on X (see below).

Follow us on <a href="https://twitter.com/labcflores" title="Follow to @labcflores on Twitter" >@labcflores <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/X_logo-black.png" width="32px" /></a>

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 11 ------------------ -->

<a name="How-to-cite"></a>

## How to cite this work

> Please, see the references with published papers by our group. In addition, please, follow the 'License and Attribution' section to cite this repository.

> Updated results will be available soon.
 
<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>


<hr>
<!-- ------------------ SECTION 12 ------------------ -->

<a name="Update logs"></a>
## Update logs

> April 25, 2025. GEBRA™ results were added to the benchmarking.

> January 9, 2024. This repository became fully public. Enjoy the reading! ;=)

> January 4, 2024. Created the private version of this repository.

<p align="right">
  <a href="#Variants-prioritizers" title="Up">
    <img src="https://github.com/genomicsITER/benchmark-germline-variants-prioritizers/blob/main/images/home-icon.png" style="float: right; margin: 10px; padding: 2 px;" />
  </a>
</p>
