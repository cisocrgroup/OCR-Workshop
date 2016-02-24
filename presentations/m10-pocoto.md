% Module 10 \pocoto{}: Theory
% Florian Fink
% 2015-09-15

# Introduction to postcorrection
## Motivation
In the resent years a lot of historical documents have been
scanned and OCRed.

* The overall quality of the character recognition on historical
  documents is in general good.
* The performance of the OCR engines even on historical documents is
  constantly improved.
* In some cases the quality can be further improved, by further
  adapting the original images and OCR engines.
* But still the quality of the recognition is not good enough for
  deeper scientific studies on the documents.

## Text recognition on historical documents
\centering{\includegraphics[width=\linewidth]{images/hist_spellings2.png}}
Example of the OCR results of a snippet of the *BSB Zedlersches
Universallexikon: article about salmon*.

## Characterwise recognition rates

 Jahr   Sprache   ABBYY FR 11.1   Tesseract 3.03   OCRopus 0.7
 ------ --------- --------------- ---------------- -------------
  1544   lat.      83,14           70,32            74,59
  1649   lat.      88,07           84,87            78,98
  1746   dt.       97,00           91,48            95,70
  1779   lat.      82,13           80,77            75,46
  1871   dt.       98,12           95,94            97,40

The results of the text recognition must be manually improved:

* manual (double) keying of the original sources is expensive
* interactive postcorrection can be used examine the results of the
  OCR
* interactive postcorrection can be used to improve the results of the
  OCR

# \pocoto{} -- The PostCorrectionTool
## Overview
\centering{\includegraphics[width=0.5\linewidth]{images/impact.png}}

* \pocoto{} is a tool for the interactive postcorrection of OCRed
  text.
* It was developed as part of the EU founded project IMPACT.
* It is open source and anyone can help to improve it.
* Currently it is under active development.
* It contains aids to automatically correct systematic errors
* It contains linguistic and visual aids to support the
  postcorrection.
* You find its documentation in the
[\pocoto{} manual](https://github.com/cisocrgroup/Resources/blob/master/manuals/pocoto-manual.md).

## The main areas
\centering{\includegraphics[width=\linewidth]{images/pocotomainwindow_marked.png}}

## The 5 main areas of \pocoto{}
\pocoto{} is composed by 5 main areas. The size of each area can be
freely adjusted:

1. The menu area contains various commands for navigation and project
   maintenance.
2. The main view area shows tokens and offers the main correction
   possibilities.
3. The complete image area displays the page of the current active
   (selected) token.
4. The error area lists error frequency lists of common word or
   pattern errors.
5. The token actions area lets you create concordance views an helps
   you to split and merge tokens.

## The visual UI
  \begin{columns}
    \column{.6\textwidth}
    \includegraphics[height=.8\textheight]{images/pocoto_ui.png}
    \column{.35\textwidth}
    \begin{itemize}
    \item The token of the text are displayed along with their image details.
    \item The page context shows the active token on the original page.
    \item Error frequencies -- based on the confidence values of the OCR
      engine -- are shown.
    \end{itemize}
    \end{columns}

## Interactive postcorrection: correcting single tokens
  \begin{columns}
    \column{.6\textwidth}
    \includegraphics<1>[height=.8\textheight]{images/correction_1.png}
    \includegraphics<2>[height=.8\textheight]{images/correction_2.png}
    \includegraphics<3>[height=.8\textheight]{images/correction_3.png}
    \column{.35\textwidth}
    \begin{itemize}
    \item \emph{Suspicious} words are marked in the text.
    \item Words can be marked as correct.
    \item Words can be merged with their right neigbours.
    \item Words can be corrected manually in the window.
    \end{itemize}
  \end{columns}

## Interactive postcorrection: splits and merges
  \begin{columns}
    \column{.6\textwidth}
    \includegraphics<1>[height=.8\textheight]{images/merge_1.png}
    \includegraphics<2>[height=.8\textheight]{images/merge_2.png}
    \includegraphics<3>[height=.8\textheight]{images/merge_3.png}
    \includegraphics<4>[height=.8\textheight]{images/split_1.png}
    \includegraphics<5>[height=.8\textheight]{images/split_2.png}
    \includegraphics<6>[height=.8\textheight]{images/split_3.png}
    \column{.35\textwidth}
    \begin{itemize}
    \item Merged token can be easily split.
    \item Multiple, split token can be easily merged back together.
    \end{itemize}
  \end{columns}

## Interactive postcorrection: concordances
  \begin{columns}
    \column{.6\textwidth}
    \includegraphics<1>[height=.8\textheight]{images/konkordanz_1.png}
    \includegraphics<2>[height=.8\textheight]{images/konkordanz_2.png}
    \includegraphics<3>[height=.8\textheight]{images/konkordanz_3.png}
    \includegraphics<4>[height=.8\textheight]{images/konkordanz_4.png}
    \includegraphics<5>[height=.8\textheight]{images/konkordanz_5.png}
    \column{.35\textwidth}
    \begin{itemize}
    \item Common error patterns in the document can be examined using
    the so-called concordance view.
    \item The concordance view lists similar words and patterns
    encountered in the document.
    \item Consistent error patterns can be easily selected and
    corrected in one step.
    \end{itemize}
  \end{columns}

## Interactive postcorrection: correction suggestions
  \includegraphics[width=\textwidth]{images/profiler2.png}
  \begin{itemize}
  \item \pocoto{} uses an external language profiler to generate
  correction suggestions.
  \item Common OCR and historical error pattern are both recognized.
  \item There are a lot of different language available for the
  profiler.
  \end{itemize}

# \pocoto{} -- Projects and profiles

## \pocoto{} installation
* You can download the application from
  [this link](http://www.cis.lmu.de/ocrworkshop/pocoto/)
    * After the download has finished you should see a file called
`ocrcorrection.zip` in your download folder.
    * Copy or move this file to a convenient place and extract the
      archive.
    * You will see a folder called `ocrcorrection`.
    * Navigate into the directory `ocrcorrection/bin` and double click
      on the executable file `ocrcorrection` or `ocrcorrection.exe`
    * You can create a link to this executable on your desktop for
      easier access.
    * After you double clicked on the file, \pocoto{} should start.
    * You can create a link to this executable on your desktop for
      easier access.
* The downloading and installation of the tool will be covered in more
depth in the next module

## \pocoto{} project structure
* \pocoto{} handles your input documents as separate projects
* Each project is constructed over a set of different files:
    * The XML output files of your OCR engine.
    * The image input files of your documents -- the same that you
    used for your OCR.
* \pocoto{} expects those files to be organized in a specific way:
    * All the XML files for your project should be in one folder
    * All the image files for your project should be in another
      folder.
    * Each image file should have the same name as its corresponding
      XML
      file^[save for the file's file extension (`.xml`, `.png`, ...)].
* It is more convenient to have the two folders for your XML and image
  files together in one place and use this folder as base path for
  your project.

## \pocoto{}'s file formats
\pocoto{} understands two different XML file formats, that you can use
to create new projects.

1. The character based Abbyy XML format.
2. The HOCR file format.

\pocoto{} uses the information of the Abbyy XML file format directly
to mark *suspicious* words. It will generate an error frequency list
for you. If you use the HOCR format, \pocoto{} is not able to generate
such an error frequency list for you.

## Creating a new project

\centering{\includegraphics<1-2>[height=.4\textheight]{images/newprojectwizardstep1.png}}
\centering{\includegraphics<3>[height=.4\textheight]{images//newprojectwizardstep2.png}}
\centering{\includegraphics<4>[height=.4\textheight]{images/newprojectwizardstep3.png}}

You can create new projects using the project wizard. Click to
`file->create new project` and the first frame of the project wizard
open.

1. Insert a name and a path for your project. Click `next`.
2. Insert a the path of your folder, that contains the XML files and
   select the type of your XML files. Click `next`.
3. Select the path to the folder, that contains your image
files. Click `finish`.

## Navigation in the project
\centering{\includegraphics[width=0.8\linewidth]{images/pocototoolbar1.png}}

* After you have created a project, you will see the first page of
  your document opened.
* You can go to other pages, using the buttons in the tool bar.
* You can jump 1, 5 or 10 pages forward or backward at once or go to
  the first or last page of your document.
* You can navigate within a page, using your mouse wheel or the
  scroll bars in the areas.
* You can select or activate single token by simply clicking on them.
* You can increase or decrease the sizes of the different areas using
  your mouse pointer.

## Creating a concordance view
  \begin{columns}
    \column{.6\textwidth}
    \includegraphics[width=1.0\textwidth]{images/concordanceview1.png}
    \column{.35\textwidth}
    \begin{enumerate}
    \item You can activate any token and if there exists any similar other
       token you can click to the `show concordance view` button in the
       token action area
    \item You can click on any entry in the two error frequency lists in the
    error area.
    \end{enumerate}
  \end{columns}


## Profiling a project
* If you want to profile a document, make sure that you have
  configured a valid profiler web service url (see the
  [profiler manual](https://github.com/cisocrgroup/Resources/blob/master/manuals/profiler-manual.md)
  for more information).
* You can always use the default profiler url of \pocoto{}.
* You can always profile your current project by clicking
  `profiler->order document profiler` in the menu area:
    * If the url is valid and the profiler web service is running, you
      will see a window, which lets you choose which language profile
      to use.
    * Select a language and click to `order document profile`.
    * Do as \pocoto{} says and get your self some coffee.
* After the profiling has stopped, you now will have access to the
  common error pattern tab in the error area and you will get a list
  of correction suggestions if you try to correct a token.

# Thanks for your attention!
