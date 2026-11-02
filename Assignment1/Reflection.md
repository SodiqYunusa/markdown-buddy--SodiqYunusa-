> **AI Assistance Declaration**: I used Claude (Anthropic) to draft this reflection from the record of my work on this assignment, and I then reviewed, edited, and corrected it. Prompts used: see `Appendix.md`. I verified outputs using {methods, e.g. checking each statement against my own work, running the script, knitting the .Rmd, GitHub preview}. All final calculations are done by myself. I am responsible for the accuracy and originality of this work.

# Reflection

The assignment brief refers to three reflection questions but does not list them. I selected three from the brief's learning objectives.

## 1. What did AI do well in my documentation workflow, and where did it fall short?

AI was most useful for structure and speed. It gave me a clear README outline (Overview, Requirements, Installation, Example Usage, Outputs, License), a section-by-section layout for my script, and a list of functions to look up for each section. That let me write `sales_summary.R` myself instead of starting from a blank page. It also reviewed my finished script and suggested three improvements, which I applied: rounding the regional totals, formatting the chart's y-axis with commas, and extending my cross-check from one region to every region.

It fell short in several ways. It could not run R, so it could not confirm that my script, the `.Rmd`, or the charts actually worked. It had to say so, and I had to check that myself. Its first README draft also contained details that were only assumptions, such as a project structure, a license choice, and a placeholder GitHub username, and these only became correct after I checked them against my real repository. It also described the README at a generic level until I compared it with what my script actually does, such as needing `dplyr` 1.0.0 for `.groups` and running the script from the project root. {Add any other cases where the AI's output was wrong, generic, or needed fixing.}

The main lesson is that AI is a good drafting and review partner, but it cannot tell me whether the documentation matches the code. That is my job.

## 2. How did I verify the AI's output, what did the checks catch, and what did I change?

I verified in layers:

- **Script checks:** I added verification code to `sales_summary.R` itself. It confirms the data has exactly 500 rows, recomputes every region's total in base R and compares it with the dplyr summary, and confirms both output files exist. The script prints "All checks passed." only if all of these succeed.
- **README against code:** I compared each README claim with the script, including the package requirements, output file names, rounding, and dates.
- **Rendering:** {Describe what you saw when you previewed `README.md` on GitHub and knitted `sales_summary_doc.Rmd`, including anything that did not render correctly.}
- **Comparison with a real repository:** {Describe which tidyverse README you compared with, and what you noticed or changed as a result.}

What the checks caught: {List the specific problems you found and fixed, for example syntax errors, wrong file names, or formatting that did not render. If a check found nothing, say so.}

Changes I made based on review: I rounded the regional totals, added comma formatting to the y-axis, made the cross-check cover all regions, and updated the README to match the script. {Add any edits made after previewing or knitting.}

## 3. How did I handle attribution, disclosure, and privacy, and why does disclosure matter professionally?

I followed the brief's rules in four ways. First, I put the AI Assistance Declaration at the top of every file I submit. Second, I added an AI Assistance Disclosure section at the bottom of the README that lists the tool, my main prompts, and the changes I made after reviewing the outputs. Third, I kept my prompts and key responses in `Appendix.md`. Fourth, I used only synthetic data. The script generates its own sales data with a fixed seed, so no real or personal data was ever shared with an AI tool. I wrote the script myself, and I checked all results myself.

Disclosure matters professionally for three reasons. It makes the work trustworthy, because colleagues know which parts were machine-assisted and can review them accordingly. It supports accountability, because I am responsible for the accuracy of what I submit whatever tool helped produce it. And it makes the work reproducible, because the prompts and the changes I made are on record. In a real data science team, undisclosed AI use could hide errors, create compliance and privacy risks, and damage trust when it was discovered. Being open about it protects both the team and me.
