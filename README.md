# Instruction of PDC package
This package includes Matlab scripts and several datasets for demo of PDC approach:
(a)	main_PDC.m is a Matlab function for the routine of experimental analysis.

(b)  main_PDC.m is the main script to call PDC by supplying following parameters:
    (1)	expression_tumor_fileName: the directory locating of the gene expression data as the input data.
    (2)	expression_normal_fileName: the directory locating of the copy number variations data as the input data.

 (c) Algorithm_PDC directory includes Matlab scripts for each step of PDC analysis, and called in main_PDC.m

(d) The input datasets include:
(1) tumor.txt: the tumor expression data in cancer.
(2) normal.txt: the normal expression data in cancer.
(3) Network_index:denotes which network PDC will use.
%if Network_index =1,PDC uses synthetic lethality genes interactions dataset (SynLethDB) collected from a variety of sources(Guo, J., Liu, H. and Zheng, J. (2016) SynLethDB: synthetic lethality database toward discovery of selective and sensitive anticancer drug targets, Nucleic Acids Research, 44, D1011-D1017.). 
 %if Network_index=2,PDC uses the reference GeneInteractionNetwork (GIN) (Hou, J.P. and Ma, J. (2014) DawnRank: discovering personalized driver genes in cancer, Genome medicine, 6, 56.) collected with literature retrieval or theoretical pre-diction. 
%if Network_index=3,PDC uses the human signal PPI network (sPPI) constructed by Vinayagam A, et al.(Vinayagam, A., Stelzl, U., Foulle, R., Plassmann, S., Zenkner, M., Timm, J., ... & Wanker, E. E. (2011). A directed protein interaction network for investigating intracellular signal transduction. Sci. Signal., 4(189), rs8-rs8.). 
(4) Control_method_index:denotes which control method PDC will use.
%if Control_method_index =1,PDC uses our iNCUA control method. 
 %if Network_index=2,PDC uses the Minimum Dominating Sets based control method(Nacher, J.C. and Akutsu, T. (2012) Dominating scale-free networks with variable scaling exponent: heterogeneous networks are not difficult to control, New Journal of Physics, 14, 73005-73028(73024).）. 
%if Network_index=3,PDC uses the Linear control theory based control method(Liu, Y.-Y., Slotine, J.-J. and Barabási, A.-L. (2011) Controllability of complex networks, Nature, 473, 167;Yuan, Z., Zhao, C., Di, Z., Wang, W. X., & Lai, Y. C. (2013). Exact controllability of complex networks. Nature communications, 4, 2447.). 
%if Control_method_index=4,PDC uses minimum FVS based method
%Chakradhar, S.T., A. Balakrishnan, and V.D. Agrawal, An exact algorithm for selecting partial scan flip-flops. Journal of Electronic Testing, 1995. 7(1-2): p. 83-93.

Note: Our PDC outputs the information of samples with paired data in the both two files.

(e) The variable “Result_predict_drug” and“NC_genes” is the output of our PDC, indicting the predicted individual combinational drugs and the target genes. For “Result_predict_drug”,the first column is the sample name with paired data (normal and tumor) and the second column is the ranked combinational drug name in descend with defined scores. For “NC_genes”,the first column is the sample name with paired data (normal and tumor) and the second column is the epistasis control genes within the breast cancer genes.

(f) As a demo, users can directly run main_PDC.m in Matlab. We choose the BRCA cancer data as a test case in our demo. We have test my PDC code in “Demo_main_test_BRCA.m”. This package has been tested in different computer environments as: Window 7 or above; Matlab 2014 or above.
(g) When users analyzed yourself new data, please:
   (1) Prepare input datasets as introduced in (d).
   (2) Clear the previous results.
   (3) Set parameters in main_PDC.m as introduced in (b).
   (4) Run main_PDC.m.
   (5) Suggest that the users add all fille in our folders to your folder.

%   $Id: main_PDC.m Created   by Weifeng Guo, Northwestern Polytechtical University, China at 2018-08-22 16:25:22 $
%   $Copyright (c) 2014-2019 by Key Laboratory of Information Fusion Technology of Ministry of Education in Northwestern Polytechnical University,and key Laboratory of Systems Biology in Shanghai Institutes for Biological Science$; 
%   $If any problem,pleasse contact shaonianweifeng@126.com for help. $
