# About W.O.U.T.E.R.

W.O.U.T.E.R. stands for Word Ontology, Unified Termbase and Exportable Reference. It is a tool that allows technical writers and translators to produce a simple multilingual glossary, gradually enrich it with terminological data, and finally export it to a TBX terminology file that can be used in many professional translation and terminology management tools.

The use case for W.O.U.T.E.R. is simple: most technical writers and translators will at some point try to manage the use of terminology in their organization by creating glossaries. Since they often don't have access to professional terminology management software, they tend to turn to Microsoft Excel. This works fine for small, monolingual glossaries, but inevitably becomes a problem when more terms and languages are added as time goes on. It is also impractical to share terminology with external parties, such as freelance translators, in this form.

W.O.U.T.E.R. allows the translator to start off in Excel, giving them a familiar environment to work in, while offering the guarantee that their work can be converted to a more scalable, flexible format later.

## Usage

### Install

Simply download the [Excel file](https://github.com/wouter-veeken/w.o.u.t.e.r./raw/master/WOUTER_v1.0.xlsm) and open it. Make sure you enable macros in Excel.

### Workflow

I created W.O.U.T.E.R. with this high-level workflow in mind:

1. Writers/translators working on a project collaboratively create and maintain a glossary on the main tab of the Excel file.
2. Over the course of the project, they gradually convert individual terms to full-fledged, multilingual concept entries.
3. As the project nears its end, definitions are finalized, obsolete/redundant terms are cleaned up, etc.
4. When the project is finished and all concepts and terms are final, the entire contents of the Excel file are exported to TBX and the file itself is abandoned.

The main point I want to stress is: W.O.U.T.E.R. is a temporary solution. It is a stepping stone to a proper terminology management tool and process.

### Create a concept entry

1. On the **Glossary** tab, enter your term and any translations in the relevant language columns.
2. Select the row containing your terms and click the **+** button at the top of the **Concept** column. This creates a new tab called **C001** (meaning 'concept 001'). Your terms/translations are on this tab.
3. Go to the **C001** tab and enter any concept and term properties you want to add (i.e. definition, word form, source reference, etc.). Note that:
    * fields marked with * are required if you plan to export your concepts/terms to TBX later;
    * fields with picklists only accept values that are in the list. These values come from the [TBX Basic](http://www.ttt.org/oscarstandards/tbx/tbx-basic.html) standard.
4. If there are multiple terms for the concept in a given language, add them by clicking the **+** button at the top of the relevant language column.

### Export concepts to TBX

1. Go to the **MRC** tab. There are two buttons at the top of this tab: **Validate** and **Export**.
2. Click **Validate** to check your concept entries for missing required properties. Invalid concepts will be marked in red, valid concepts in green.
3. Complete any missing properties and validate again until all concepts are marked green.
4. Click **Export**. Your concept entries are translated into the vertical MRC format and appear on the sheet.
5. Copy the contents of the MRC tab to a plain text editor and save.
6. Go to [TBX Convert](http://www.tbxconvert.gevterm.net/mrc2tbx/index.html) and upload your file.

The resulting TBX file can be used in programs such as [SDL MultiTerm](http://www.sdl.com/solution/language/terminology-management/multiterm/), [XBench](https://www.xbench.net/), [OmegaT](http://www.omegat.org/) and most other translation and terminology management tools.

## Known limitations

* Only 7 languages are currently supported: English (US), English (GB), Norwegian, Swedish, Dutch, Finnish, Danish. (If you have knowledge of Visual Basic, you can change the languages by editing the `Buttons_` module.)
* Conversion from MRC to TBX is dependent on [TBX Convert](http://www.tbxconvert.gevterm.net/mrc2tbx/index.html).
* No synchronization between **Glossary** tab and concept tabs: changes made to concepts are not automatically reflected in glossary. This is deliberate – W.O.U.T.E.R. is intended to be a temporary solution.
