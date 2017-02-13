********************************************************************************
********************************************************************************




********************************************************************************
*                          ---- SpecOMS README ----                            *
********************************************************************************
*                                                                              *
*   Version:                                                           1.0.0   *
*   Date:                                                         01/02/2017   *
*   Author:                                                   Matthieu DAVID   *
*                                                                              *
*   This  software  is licensed  under the  Apache 2  license, quoted below.   *
*                                                                              *
*   Copyright 2017 Institut National de la Recherche Agronomique, Université   *
*   de Nantes.                                                                 *
*                                                                              *
*   Licensed under the Apache  License, Version 2.0 (the "License"); you may   *
*   not use this  file except in compliance with the License. You may obtain   *
*   a copy of the License at                                                   *
*                                                                              *
*      http://www.apache.org/licenses/LICENSE-2.0                              *
*                                                                              *
*   Unless  required by  applicable law  or agreed  to in  writing, software   *
*   distributed  under the  License  is  distributed  on an  "AS IS"  BASIS,   *
*   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.   *
*   See the License  for the  specific  language governing  permissions  and   *
*   limitations under the License.                                             *
*                                                                              *
********************************************************************************




********************************************************************************
*                                                                              *
*                             TABLE OF CONTENTS                                *
*                                                                              *
********************************************************************************
*                                                                              *
*   SpecOMS - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -    1   *
*            What is SpecOMS ?  - - - - - - - - - - - - - - - - - - - -  1.1   *
*            SpecOMS advantages - - - - - - - - - - - - - - - - - - - -  1.2   *
*            SpecOMS limitations  - - - - - - - - - - - - - - - - - - -  1.3   *
*                                                                              *
*   SpecOMS usage - - - - - - - - - - - - - - - - - - - - - - - - - - -    2   *
*            prerequisites  - - - - - - - - - - - - - - - - - - - - - -  2.1   *
*            installation - - - - - - - - - - - - - - - - - - - - - - -  2.2   *
*            configuration  - - - - - - - - - - - - - - - - - - - - - -  2.3   *
*            execution  - - - - - - - - - - - - - - - - - - - - - - - -  2.4   *
*                                                                              *
*   Files structure - - - - - - - - - - - - - - - - - - - - - - - - - -    3   *
*            database source file - - - - - - - - - - - - - - - - - - -  3.1   *
*            contaminants file  - - - - - - - - - - - - - - - - - - - -  3.2   *
*            experimental spectra file  - - - - - - - - - - - - - - - -  3.3   *
*            results file - - - - - - - - - - - - - - - - - - - - - - -  3.4   *
*                                                                              *
*   Contact - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -    4   *
*                                                                              *
********************************************************************************




********************************************************************************
*                                 1. SpecOMS                                   *
********************************************************************************

*------------------------------------------------------------------------------*
|                            1.1 What is SpecOMS ?                             |
*------------------------------------------------------------------------------*
|                                                                              |
|   SpecOMS is an Open Modification Search  software designed for rapid        |
|   identification of important datasets of experimental spectra produced      |
|   through tandem mass spectrometry.                                          |
|                                                                              |
|   If you use SpecOMS, please do cite the following work: SpecOMS: Rapid      |
|   interpretation of discovery proteomics experiments with an open            |
|   modification search strategy, M.David, G.Fertin, H.Rogniaux.               |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            1.2 SpecOMS advantages                            |
*------------------------------------------------------------------------------*
|                                                                              |
|   SpecOMS exhibits two major advantages in comparison with other existing    |
|   approaches that do not use a preliminary mass filter:                      |
|       - the software is very efficient and can propose identifications for   |
|         thousands of experimental spectra using a reference database         |
|         containing hundreds of thousands of spectra within a few minuts.     |
|       - as the search neighborhood remains the same for any spectra the      |
|         FDR can be reliably estimated for modified peptides.                 |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            1.3 SpecOMS limitations                           |
*------------------------------------------------------------------------------*
|                                                                              |
|   The major known limitation in the use of SpecOMS is the quality of the     |
|   experimental dataset. Indeed consistent and reliable matching can only     |
|   be reliably achieved wwhen experimental data have been acquired using      |
|   a high-accuracy tandem mass spectrometer to achieve the best possible      |
|   accuracy for the ion fragments.                                            |
|                                                                              |
|   SpecOMS has been developped and tested under Windows7 64bits with java     |
|   SE 8, compatibility with another operating system or configuration may     |
|   exist but is not ensured.                                                  |
|                                                                              |
*------------------------------------------------------------------------------*




********************************************************************************
*                                 2 SpecOMS usage                              *
********************************************************************************

*------------------------------------------------------------------------------*
|                            2.1 prerequisites                                 |
*------------------------------------------------------------------------------*
|                                                                              |
|   SpecOMS has been developped and tester under a windows7 64bits             |
|   environment. Compatibility with other operating systems or windows         |
|   versions might exist but is not ensured.                                   |
|                                                                              |
|   The algorithm has been developped using functions available only in        |
|   java 1.8. It is therefore necessary for the user to have a Java Runtime    |
|   Environment compatible with java 1.8 (preferably 64bits).                  |
|                                                                              |
|   The Java Standard Environment 1.8 for windows can be found at the          |
|   following url:                                                             |
|                                                                              |
|      http://www.oracle.com/technetwork/java/javase/downloads/index.html      |
|                                                                              |
|   SpecOMS  should  preferably be used  on a server  version of the jvm for   |
|   efficiency  purposes. However, it  can be executed on a standard version   |
|   with no major drawback by removing the  -server parameter in the command   |
|   line instruction.                                                          |
|                                                                              |
|   To simply execute SpecOMS from the provided execution script you need to   |
|   ensure the presence of java into the path variable of your operating       |
|   system. For more information, consult the following url:                   |
|                                                                              |
|   https://docs.oracle.com/javase/tutorial/essential/environment/paths.html   |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            2.2 installation                                  |
*------------------------------------------------------------------------------*
|                                                                              |
|   No specific installation is required for the execution of SpecOMS once     |
|   the prerequisite are met. The software is immediately executable from      |
|   the .jar file available in the archive. The user should however first      |
|   configure the parameters in the joint files as explained thereafter.       |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            2.3 configuration                                 |
*------------------------------------------------------------------------------*
|                                                                              |
|   Two configuration files are provided with SpecOMS . Their presence and     |
|   correct syntax is a mandatory requirement for a proper execution of the    |
|   software. In case of an obvious malfunction of the software, the user      |
|   should first ensure that those requirements are met.                       |
|                                                                              |
|   In case of doubts, a minimal example of the configuration files can be     |
|   obtained executing the generate_config_files.bat script present into       |
|   the archive. Parameters and paths files values can then be adjusted by     |
|   the user to fit its needs.                                                 |
|                                                                              |
*------------------------------------------------------------------------------*
|                            2.3.1 files_config.ini                            |
|------------------------------------------------------------------------------|
|                                                                              |
|   This first file contains all needed information about the location of      |
|   the datasets used by SpecOMS. Its content consist in 4 lines. Each line    |
|   mentions a file path (including the name and the extension of the file)    |
|   indicated using relative positionning with regard to the .jar executable   |
|   of SpecOMS location.                                                       |
|                                                                              |
|      Line 1: database source file location                                   |
|      Line 2: contaminant file location                                       |
|      Line 3: experimental spectra dataset file location                      |
|      Line 4: location of the result file produced by SpecOMS                 |
|                                                                              |
|   Each of those files have a mandatory structure detailed in section 3       |
|                                                                              |
|------------------------------------------------------------------------------|
|                            2.3.2 execution_parameters.ini                    |
|------------------------------------------------------------------------------|
|                                                                              |
|   This file contains the parameters used for the execution of SpecOMS. They  |
|   are given under the form of key=value pairs with no order constraint.      |
|   Valid parameters are detailed thereafter with the default value if the     |
|   parameter key is detected as missing. Advices on the value range are       |
|   also given when relevant.                                                  |
|                                                                              |
|      decoyBase=x                                                             |
|      Boolean value (true - false)                                            |
|      Default value is false                                                  |
|      If set on true, the database is transformed into a decoy database       |
|      using a peptide reverse method, reversing all amino-acids except the    |
|      last into each peptide after digestion.                                 |
|                                                                              |
|      minimumPeptideLength=x                                                  |
|      Integer value                                                           |
|      Default value is 7                                                      |
|      Minimum allowed length for peptide created during in silico digestion   |
|      of the protein database (inclusive value). All generated peptides       |
|      strictly shorter are simply discarded.                                  |
|                                                                              |
|      maximumPeptideLength=x                                                  |
|      Integer value                                                           |
|      Default value is 25                                                     |
|      Maximum allowed length for peptide created during in silico             |
|      digestion of the protein database (inclusive value). All generated      |
|      peptides strictly longer are simply discarded.                          |
|                                                                              |
|      threshold=x                                                             |
|      Integer value                                                           |
|      Default value is 8                                                      |
|      Minimum number of shared masses required for a PSM to be further        |
|      examined by SpecFit. PSMs with a strictly lower score are discarded.    |
|      Too small threshold value should not be used as it may slightly         |
|      increase the sensitivity of the method, but would probably lead         |
|      to a drastic increase in the number of false positive                   |
|      identifications. On opposite, a very high value would increase the      |
|      confidence in the obtained identifications at the cost of               |
|      sensitivity.                                                            |
|                                                                              |
|      maxMassesCount=x                                                        |
|      Integer value                                                           |
|      Default value is 50                                                     |
|      Limit the number of peaks that are kept for each experimental           |
|      spectrum after reading the experimental datafile. Peaks with the        |
|      smallest intensity are discarded in priority. However, no peaks are     |
|      kept into a +- 0.4 Da window, which can lead to discard peaks with      |
|      higher intensities than some peaks kept. If a spectrum contains less    |
|      than 20 peaks, the spectrum is automatically discarded without          |
|      further processing (it doesn't contain enough information to ensure     |
|      result reliability).                                                    |
|                                                                              |
|      minimumSpectrumCharge=x                                                 |
|      Integer value                                                           |
|      Default value is 1                                                      |
|      Experimental spectra with a stricly smaller count of charge are         |
|      discarded.                                                              |
|                                                                              |
|      maximumSpectrumCharge=x                                                 |
|      Integer value                                                           |
|      Default value is 3                                                      |
|      Experimental spectra with a stricly higher count of charge are          |
|      discarded. One should be cautious while increasing the tolerance on     |
|      the charge value for experimental spectra as the higher the charge      |
|      is, the more (and less accurate) peaks the spectrum contains,           |
|      increasing the risk of producing a spurious match for this spectrum.    |
|                                                                              |
|      numberOfDecimals=x                                                      |
|      Integer value                                                           |
|      Default value is 2                                                      |
|      Order of magnitude used for the scaling of floating point value into    |
|      integers.                                                               |
|                                                                              |
|      decimalValue=x                                                          |
|      Integer value                                                           |
|      Default value is 2                                                      |
|      Value of the decimal used for the framgent ion mass accuracy. Leads     |
|      to the insertion of the exact mass value m and all supplementary        |
|      masses between m-x and m+x.                                             |
|                                                                              |
|   The combination of the parameters numberofDecimals and decimalValue        |
|   should be as close as possible to the fragment ion accuracy used for the   |
|   acquisition of the experimental dataset processed using the software       |
|   suite. For example if the experimental spectra dataset has                 |
|   been acquired with a fragment ion accuracy of 0.04Da, the parameter        |
|   numberOfDecimals should be set to 2 (multiplication by 100 top reach an    |
|   integer value) and the decimal value to 4 in order to ensure the proper    |
|   support of the accuracy by the software. A dataset acquired with an        |
|   accuracy of 0.5Da on the fragment ion masses leads to the following        |
|   paramters: numberOfDecimals=1 and decimalValue=5. One should notice        |
|   however that the extended search space for each spectrum might lead to     |
|   an important number of spurious fragment mass collisions in the case of    |
|   an unsufficient accuracy at the level of the data acquisition.             |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            2.4 execution                                     |
*------------------------------------------------------------------------------*
|                                                                              |
|   Once all configuration and source files are set up, SpecOMS can be         |
|   simply executed by double-clicking the SpecOMS.bat file (this require      |
|   java to be properly set in your operating system path and the system to    |
|   have at least 8GB of memory).                                              |
|                                                                              |
|   The software can also be manually launched in a terminal using the         |
|   traditionnal command line for jar files: java SpecOMS.jar                  |
|                                                                              |
|   If started using the command line, we recommend the use of the             |
|   following parameters in the command line:                                  |
|                                                                              |
|      -d64                                                                    |
|      -server                                                                 |
|      -XX:+AggressiveOpts                                                     |
|      -XX:+UseFastAccessorMethods                                             |
|      -XX:+UseConcMarkSweepGC                                                 |
|      -XX:+UseParNewGC                                                        |
|      -Xmx0g where the zero should be replaced by the allocated space in      |
|       memory for the virtual machine in gigagabytes (for common proteomics   |
|       datasets, this value should be set to 4 except if the system does      |
|       not own at least 4GB of memory, in which case this SpecOMS might       |
|       be considerably slow down).                                            |
|                                                                              |
|   Note that those command line arguments are not available for all JVMs      |
|   and therefore the user should stick to the oracle JVM version.             |
|                                                                              |
|   In case the user does not want to add this version of the virtual          |
|   machine to its operating system path, the command line can still be        |
|   executed prefixing the "java" keyword with the absolute path of the JVM    |
|   on the user's operating system.                                            |
|                                                                              |
*------------------------------------------------------------------------------*




********************************************************************************
*                            3 Files structure                                 *
********************************************************************************
*                                                                              *
*   The following sections give information on the mandatory structure of      *
*   each data file and explanations on each field. Typical files are           *
*   available in the "data" folder aside SpecOMS to provide examples for the   *
*   user if needed. Those files might however not be biologically relevant     *
*   and are provided only as examples.                                         *
*                                                                              *
********************************************************************************

*------------------------------------------------------------------------------*
|                            3.1 database source file                          |
*------------------------------------------------------------------------------*
|                                                                              |
|   The database source file is organised as a sequence of proteins            |
|   following each other.                                                      |
|                                                                              |
|   Each protein is composed of at least two lines.                            |
|                                                                              |
|   The first line of a protein is constituted of any sequence of caracters    |
|   needed by the user to reference the protein, starting with the caracter    |
|   '>'.                                                                       |
|                                                                              |
|   On the second line and all the next until another caracter '>' comes the   |
|   amino acid sequence forming the protein. Characters representing the       |
|   amino acids should be conventionnal characters for the representation of   |
|   amino-acids and should not be split by any kind of separator. The          |
|   sequence can be split on multiple line or kept on a single one without     |
|   affecting the behaviour of SpecOMS.                                        |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            3.2 contaminants file                             |
*------------------------------------------------------------------------------*
|                                                                              |
|   The contaminant file is formatted in the same way as the database source   |
|   file. If the user does not want to include contaminants in the             |
|   computations then a blank file should be used instead.                     |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            3.3 experimental spectra file                     |
*------------------------------------------------------------------------------*
|                                                                              |
|   This .mgf file contains all the experimental spectra, each of the          |
|   spectra formatted in its own segment with the following syntax.            |
|                                                                              |
|   A spectrum segment must start with the "BEGIN IONS" line and end with      |
|   the "END IONS" line. Inside the segment, the following lines must be       |
|   present in any order, preferably just after the "BEGIN IONS" (text in      |
|   parentheses must not be included and is there only for description).       |
|                                                                              |
|      Title=b1922_293T_proteinID_02A_QE3_122212.raw (Title of the dataset     |
|      from which the spectrum comes from)                                     |
|                                                                              |
|      SCANS=2042 (Scan number of the spectrum in the experiment)              |
|                                                                              |
|      CHARGE=3+ (Charge state of the spectrum)                                |
|                                                                              |
|      PEPMASS=374.1871 (Observed mass for the parent ion)                     |
|                                                                              |
|   After those information and before the end of the spectrum segment come    |
|   peak mass and intensity values expressed as a pair of floating point       |
|   values as follow : 114.0781 2261.7. Values of mass and intensity must be   |
|   separed by a space and each peak must be written on its very own line.     |
|                                                                              |
|   Experimental spectra can be written one after each other or separed by     |
|   a blank line. An example file containing a few spectra is given in the     |
|   archive to help the user if needed. Alternative mgf syntax might work      |
|   but the correctness of the result is not ensured.                          |
|                                                                              |
*------------------------------------------------------------------------------*

*------------------------------------------------------------------------------*
|                            3.4 results file                                  |
*------------------------------------------------------------------------------*
|                                                                              |
|   The result of SpecOMS execution is stored in the result file indicated     |
|   by the user as a collection of PSM, one on each line.                      |
|                                                                              |
|   For a given PSM, multiple values are displayed separated by semicolumn     |
|   as explained thereafter. The first line of the result file displays a      |
|   tag for each value so that the user can identify them easily.              |
|                                                                              |
|      spectrumID: the spectrum identifier, composed of the name of the        |
|      dataset and the scan number                                             |
|                                                                              |
|      peptide: the peptide sequence associated by SpecOMS to this spectrum    |
|                                                                              |
|      sharedMassesBeforeSpecFit: the number of masses shared between the      |
|      spectrum and the peptide before potential execution of SpecFit          |
|                                                                              |
|      sharedMassesAfterSpecFit: the number of masses shared between the       |
|      spectrum and the peptide after execution of SpecFit, should be          |
|      identical or greater than the previous value                            |
|                                                                              |
|      massDeltaLocation: location of the mass delta into the peptide          |
|      sequence to achieve the number of shared masses after SpecFit. Starts   |
|      at 0, this value is -1 if SpecFit did not improved the number of        |
|      shared masses                                                           |
|                                                                              |
|      observedMassDelta: value of the observed delta in dalton                |
|                                                                              |
|      affix: prefix or suffix sequence in case of the detection of a          |
|      missed cleavage peptide. The sequence is give between parentheses and   |
|      preceded repectively by Pref or Suff. This field is leaved blank if     |
|      there is no missed cleavage                                             |
|                                                                              |
|      cutSide: indicates a potential side on which the peptide is             |
|      truncated; the missing part is on left is the value is -1 and on        |
|      right if the value is 1 and the length of the missing sequence can be   |
|      deduced from the field massDeltaLocation. If the value is 0, then       |
|      this peptide is not a semi-tryptic peptide.                             |
|                                                                              |
|      chargeError: indicates a potential charge state error if the value is   |
|      1, it should be 0 otherwise.                                            |
|                                                                              |
*------------------------------------------------------------------------------*




********************************************************************************
*                                  4 Contact                                   *
********************************************************************************
*                                                                              *
*   In case of any trouble using SpecOMS, the author of the software can be    *
*   reached at the following address:                                          *
*                                                                              *
*      Matthieu DAVID : matthieu.david@univ-nantes.fr                          *
*                                                                              *
*   In case you suspect an incorrect behavior from the software, more          *
*   information about your dataset and configuration parameters might be       *
*   asked along with a minimal working example reproducing the problem so      *
*   that the issue can be further investigated.                                *
*                                                                              *
*   In case no answer is given to you under two weeks, we strongly             *
*   recommend you to contact this person instead:                              *
*                                                                              *
*      Dominique TESSIER : dominique.tessier@inra.fr                           *
*                                                                              *
*   Any communication should be written in english.                            *
*                                                                              *
********************************************************************************




********************************************************************************
********************************************************************************
