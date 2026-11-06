# Marcus_PhD_Thesis

This repository provides interactive companions to a doctoral thesis on olfactory transitive inference in mice. The thesis covers the establishment of a head-fixed task, post-session chemogenetic manipulation of the medial prefrontal cortex (mPFC), and Neuropixels recordings from mPFC in sleep-control and sleep-deprivation groups.

Mice were trained on four overlapping premise pairs, AB, BC, CD, and DE, and then tested on the untrained AE and BD pairs without sucrose or quinine delivery. Two viewers present the data:

| File | Contents |
| --- | --- |
| `marcus_thesis.html` | Behavior: schedules, performance charts, and individual-mouse lick rasters for all five groups |
| `marcus_mPFC_interactive_data_thesis.html` | mPFC population activity in the two Neuropixels groups, days 13–22 |

## Open the viewers

Download either file and open it in a web browser. Each file contains its data, graphics, and fonts, works offline after downloading, and requires no installation.

## Behavioral viewer

### Experiments and groups

Choose an experiment from the cards below the page header, or from the **Experiment** menu in the control bar.

| Experiment | Group | Mice |
| --- | --- | ---: |
| Behavioral establishment | Establishment | 12 |
| Chemogenetics | Vehicle | 8 |
| Chemogenetics | Deschloroclozapine (DCZ) | 8 |
| Neuropixels | Sleep control | 6 |
| Neuropixels | Sleep deprivation | 6 |

Each selection displays the corresponding behavioral schedule, performance data, and test rasters. The schedules include the timing of post-session treatment, recording and sleep deprivation where applicable.

### Explore the data

- **Behavioral schedule:** Follow the task from premise-pair training through reinforcement, randomization, novel-pair testing and reassessment. The schedule's stages align with the performance chart, and only the novel-pair tests on days 19–20 are shaded. Select **Enlarge schedule** for a closer view. The A > B > C > D > E diagram at the top of the page shows the trained premise pairs as solid arcs and the untrained test pairs, AE and BD, as dashed arcs.
- **Performance:** Hover over or tap the chart to see the mean ± SEM for that position together with every mouse’s value, sorted from highest to lowest. The odor pair under the pointer is highlighted in the diagram at the top. After selecting the chart, the left and right arrow keys move between positions. Select a mouse below the chart to highlight its curve. Black squares and error bars show the mean ± SEM across mice; the dashed horizontal line marks 50%.
- **Lick rasters:** Choose a mouse, test day and odor pair in the control bar near the top of the page; on larger screens it stays in view while you scroll. Test days 1 and 2 correspond to behavioral days 19 and 20. Each AE or BD panel shows the two odors separately, with time from odor onset on the horizontal axis and trial number on the vertical axis, and lists that mouse’s A- or B-directed licking and choice indices for the day. Black marks indicate individual licks, and red marks identify the first response-window lick on trials containing a response.
- **Lick detail:** Click a raster to inspect individual licks. Scroll to zoom in time (up to 256×) while trial spacing stays fixed, drag to pan, or use the timeline below the plots to move the displayed interval. Show a single trial, and hover over a lick to see its trial and time. **Full 0–10 s** restores the complete interval.
- **Counts and indices:** In the lick detail, expand the counts panel to see response-window lick counts, responding-trial counts, and the supplied licking and choice indices for both odors. These summaries cover all trials in the 5–10 s response window and do not change with the displayed interval or trial selection.
- **Reference raster and zoom:** In the lick detail, select **Reference raster** to open the original raster figure. Scroll over the area you want to inspect, drag to pan, or use the overview in the lower-right corner to move to another part of the plot. Zoom extends to 50× the fitted view while preserving sharp vector lines. Select **Fit** to return to the complete panel.
- **Downloads:** The performance chart, schedule, rasters and the current lick-detail view can be downloaded as SVG files using the controls in the viewer.
- **Light and dark themes:** Use the button in the top-right corner to switch themes. Charts and rasters stay on a white background in both.

Selecting an individual mouse highlights its performance curve without changing the group mean or SEM. Click “Mean ± SEM” to show or hide the mean line, markers, and error bars together. During establishment and chemogenetic randomization, performance is aligned by premise pair across mice, so hover labels identify pair-aligned positions rather than a single chronological day for each block. The Neuropixels performance chart follows the recorded day and pair sequence.

## Population activity viewer

This viewer presents mPFC Neuropixels 2.0 recordings from the sleep-control (6 mice) and sleep-deprivation (6 mice) groups on behavioral days 13–22. Each day includes two odor pairs, so each view shows four conditions: the two odors of each pair.

| Days | Stage | Odor pairs |
| --- | --- | --- |
| 13–14 | Reinforcement | AB and BC; CD and DE |
| 15–18 | Randomization | BC and CD; AB and DE; AB and CD; BC and DE |
| 19–20 | Novel-pair test | AE and BD |
| 21–22 | Reassessment | AB and BC; CD and DE |

### Explore the data

- **Cohort and day:** Choose a cohort and a recording day from the timeline below the page header; each day lists its two odor pairs. The marker between days 18 and 19 reads **6 h sleep deprivation** for the sleep-deprivation group and **Sleep** for the sleep-control group. The control bar at the top of the page stays in view while you scroll and repeats the day and cohort controls.
- **Time cursor:** Press play or drag the slider to move through the trial from −1 to 4 s relative to odor onset, covering the pre-odor period, the odor (0–2 s), and the delay (2–4 s). The cursor links the trajectories, heatmaps, decoding curve and confusion matrix. Trajectory and heatmap time points are 100-ms bins; decoding uses 1-s windows centered on the same times.
- **Population trajectories:** Rotate the three-dimensional PCA trajectories (PC1–PC3, correct trials) by dragging or with the arrow keys, and scroll to zoom. Click a point to move the time cursor to it. Select a condition in the legend to show or hide it. **Floor projection** adds each trajectory’s PC1–PC2 shadow, **Orbit** rotates the view continuously, and **Reset view** restores the starting view.
- **Activity heatmaps:** Baseline-normalized activity of each neuron for the four conditions, from correct and incorrect completed trials, on a fixed scale from −5 to +5. Scroll to zoom the rows, drag to pan, and click to set the time. Hover over a row to compare that neuron across the four conditions. **Show all rows** returns to the full population.
- **Four-class SVM decoding:** Decoding accuracy from correct trials in 1-s windows, shown as the mean ± SEM across mice with individual mice as faint lines. Each window is compared with the −1 s pre-odor window (paired t-test, uncorrected). Hover for the values in a window, or click to move the time cursor. **Decoding values for every window** lists all windows in a table.
- **Confusion matrix:** The mean proportion of predictions at the current time, with true conditions in rows and predicted conditions in columns. Hover over or focus a cell for its mean ± SEM, SD and n.
- **Similarity index:** Choose a pair of conditions to compare their PC1–PC3 trajectories over 0.5–4 s in correct trials. Both groups are shown with 95% bootstrap confidence intervals and two-sided shuffle P values (uncorrected).
- **Sleep control vs sleep deprivation:** Each point is one mouse’s mean decoding accuracy over window centers 0.5–4.0 s. Groups are compared with a two-sided Welch test, with Holm correction across the 10 days.
- **Keyboard:** <kbd>Space</kbd> plays or pauses, <kbd>←</kbd> and <kbd>→</kbd> step through time, and <kbd>[</kbd> and <kbd>]</kbd> change the day.
- **Light and dark themes:** Use the button in the top-right corner to switch themes.

## Source data

Figure-specific source data and statistical results are provided in two Excel workbooks:

| Workbook | Figures |
|---|---|
| [Thesis_Source_Data_Figures_2-24.xlsx](Thesis_Source_Data_Figures_2-24.xlsx) | 2, 3, 6–10, 15–18, 23 and 24 |
| [Thesis_Source_Data_Figures_25-28.xlsx](Thesis_Source_Data_Figures_25-28.xlsx) | 25–28 |

Worksheet names identify the corresponding figures or analyses. Both workbooks include the Statistics sheet and supporting neural-analysis sheets to preserve their formula dependencies. These shared sheets contain the same data in both files.

The viewers provide an interactive way to inspect the data accompanying the thesis. Experimental procedures, definitions of behavioral measures, the population-activity analyses and the statistical tests are described in the thesis and its source-data workbook.
