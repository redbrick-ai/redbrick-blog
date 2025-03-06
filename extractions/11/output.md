Volumetric segmentation of necrosis and edema

Ben Stewart

January 23, 2024

Overview

For this walkthrough, we will be segmenting two types of high-grade
gliomas (necrosis and edema) using various weighted scans.

Our data consists of MRI acquisitions of the following sequences: T1W,
T1W gadolinium-enhanced (i.e. T1CE), T2W, and FLAIR.

Structure 1: Edema

Before jumping into annotations on the TICE, let[']{dir="rtl"}s set up
our labeling environment.

Windowing Settings

If you[']{dir="rtl"}d like to adjust default Windowing settings, you can
do so by:

opening the Visualization Panel and adjusting the sliders, or

mousing over a viewport and using CTRL+LMB+drag

dragging your mouse left and right will adjust the Windowing Width

dragging your mouse up and down will adjust the Windowing Level

![65af8d8ffb96d90d47a7b69a_adjusting-windowing_lo.gif](extractions/11/images/media/image1.gif){width="6.4998611111111115in"
height="3.842283464566929in"}

Adjusting Windowing settings using both the panel and hotkeys

Windowing Settings Mastery

Now it[']{dir="rtl"}s time for you to try!

Your RedBrick AI environment has several sample projects that you can
use to explore the platform[']{dir="rtl"}s features.

Open any Task in the Brain Brats Study (Sample) Project

Adjust the Windowing settings by using both of the methods described
above

Zoom in on any brain scan and toggle Visual Pixel Interpolation in the
Visualization Panel to see the difference. (If you[']{dir="rtl"}re not
sure how to zoom in on a scan, click on the ["]{dir="rtl"}?" button in
the Annotation Tool or check out our documentation
[[here]{.underline}](https://docs.redbrickai.com/annotation/overview#navigating-your-volume))

Close the Visualization Panel by clicking on the ["]{dir="rtl"}X" in the
top right corner

Bonus: close the Visualization Panel without clicking on the
["]{dir="rtl"}X" in the top right corner

Your First Annotation

It[']{dir="rtl"}s time to create an annotation in RedBrick AI!  Select
Edema by clicking on the plus sign next to it in the lefthand menu.

![65af8f7bc750891066f1a411_Untitled.png](extractions/11/images/media/image1.png){width="6.4998611111111115in"
height="6.008193350831146in"}

Hotkey Alert: you could also press ["]{dir="rtl"}4" on your keyboard to
create a new Edema label.

Step Two is choosing the right tool for the job! In this case,
we[']{dir="rtl"}ll explain how to use the Contour Tool to volumetrically
segment the Edema.

2D Contour Tool

Let[']{dir="rtl"}s start by annotating a single slice.

RedBrick AI[']{dir="rtl"}s Contour Tool allows you to create precise
contours using one of three methods:

Point and click - use LMB to place points on the canvas, drawing a
contour between the points

Click and drag - use LMB+drag to draw a contour on the canvas

Smart Contouring - while holding CTRL+ALT (or CTRL+OPTION on MacOS),
hover over a boundary to automatically generate a contour. Use LMB to
create the contour, or LMB+drag to smooth the contour.

When you[']{dir="rtl"}re satisfied with a contour, be sure to Rasterize
it by either clicking on the Rasterize button in the right hand Context
Panel (see below) or by pressing SHIFT+ENTER.

![65af90ad3414fdde3fddfa9d_Untitled
(1).png](extractions/11/images/media/image2.png){width="6.4998611111111115in"
height="6.036305774278215in"}

The rasterization process transforms the contour you[']{dir="rtl"}ve
created into a segmentation mask, which applies your annotation to the
image.

The following short video demonstrates all of the 3 contouring methods
mentioned above.

![65af90e197bf1fa8617ac5c7_3-contour-types.gif](extractions/11/images/media/image2.gif){width="6.4998611111111115in"
height="3.835984251968504in"}

As you can see in the video, the Smart Contouring method does most of
the work on its own with the help of properly configured Windowing
settings.

Please note that you can also mix and match contouring methods to edit
your contour!

2D Contour Tool Mastery

Complete the tasks below to demonstrate an understanding of how to use
the Contour Tool in 2D (i.e. on a single slice):

create a contour using the point and click method

create a contour using the click and drag method

create a contour using Smart Contouring

Bonus: smooth a Smart Contour using LMB+drag

3D Contour Tool

Like many tools on RedBrick AI, the Contour Tool can be used in both 2D
and 3D. Annotating in 3D will make this work flow much faster, so
let[']{dir="rtl"}s explore how to do that with interpolation.

![65af91118386fcd2d1e05a68_Untitled
(2).png](extractions/11/images/media/image3.png){width="6.4998611111111115in"
height="3.175980971128609in"}

As the diagram shows, you can create contours over many slices at once
by contouring the first and last slices in the range. Let[']{dir="rtl"}s
see what this looks like in the Annotation Tool.

![65af919fe29d0d3daf4f270b_interpolation-lo.gif](extractions/11/images/media/image3.gif){width="6.4998611111111115in"
height="3.842283464566929in"}

After creating contours on slices 70 and 73, the Contour Tool
automatically filled in the gaps.

There are 2 common ways to edit a contour:

Continue to edit it using the Contour Tool, or

Rasterize the contour and edit the segmentation mask using any of the
other Segmentation Tools (i.e., Brush Tool, Pen Tool, Adaptive Brush,
etc.)

3D Contour Tool Mastery

Complete the following tasks to gain a basic understanding of how
interpolation works with the Contour Tool:

Create a set of 5 contours by interpolating across a range of 5 slices

With the Contour Tool selected, edit an existing contour

After rasterizing a Contour, use either the Brush Tool or the Pen Tool
to edit the segmentation mask

Bonus: interpolate across a large range of slices (30 or more) - how do
the contours you created at the end of the slice ranges affect the
interpolation?

Annotating the Edema

It[']{dir="rtl"}s time to take everything you[']{dir="rtl"}ve learned
and put it into action!

Let[']{dir="rtl"}s review the flow:

Configure Windowing settings

Create annotations using the Contour Tool and interpolation

Review the annotations using your preferred tools (e.g. Brush Tool, Pen
Tool, Contour Tool, etc.)

You can find a full video outlining the process below:

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/11/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the
Edema](https://www.loom.com/share/f499a17154cc4ab7a4214c3e30aed98b?source=embed_watch_on_loom_cta)

11 min

13 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~11 min~~

⚡️

14 min

11 min

9 min 20 sec

7 min 28 sec

6 min 35 sec

5 min 36 sec

4 min 28 sec

Your user agent does not support the HTML5 Video element.

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/11/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the
Edema](https://www.loom.com/share/f499a17154cc4ab7a4214c3e30aed98b?source=embed_watch_on_loom_cta)

11 min

13 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~11 min~~

⚡️

14 min

11 min

9 min 20 sec

7 min 28 sec

6 min 35 sec

5 min 36 sec

4 min 28 sec

Finding the best combination of tools for a given use case is one of the
most effective ways to make annotating less difficult, and
there[']{dir="rtl"}s no ["]{dir="rtl"}one size fits all" solution.

For example, my personal workflow in the video above looked like this:

Set Windowing settings for highest possible contrast around the
boundaries of the target structure

Use Smart Contouring and interpolation to rapidly create 3D annotations

Use the 2D Contour Tool to touch up individual slices as needed

Rasterize the contour, repeat Steps 2-4 until the entire structure is
completed

Disable Visual Pixel Interpolation in the Visualization Panel

Use the 3D Hole Filling Tool to ensure there are no stray empty pixels
in my 3D annotation

Use the 2D Brush Tool and 2D Pen Tool to touch up the segmentation masks
on each slice

Save my work

For now, we can move on to our next structure - Necrosis.

Structure 2: Necrosis

Now that we have our Edema label in place, it[']{dir="rtl"}s time to add
some Necrosis labels!

Windowing Settings Mastery

Using the knowledge you gained above, make sure your Windowing settings
are configured in anticipation of annotating Necrosis inside of the
brain tumors.

We[']{dir="rtl"}re going to want to maximize the pixel contrast between
the Necrosis and the surrounding Edema.\
\
Read on to learn why!

For this part of the walkthrough, we[']{dir="rtl"}re going to let you
decide how to configure your environment. Please find a list of
environment settings below.

Configure your Windowing settings

Configure your pixel interpolation toggle

Configure your Layout

Label Actions

There are many things that can be done with labels in RedBrick AI, and
we call these functions Label Actions.

![65af926ab48a4f988d3e7f3d_Untitled
(3).png](extractions/11/images/media/image4.png){width="6.4998611111111115in"
height="6.563429571303587in"}

We have more [[in-depth documentation
elsewhere]{.underline}](https://docs.redbrickai.com/annotation/creating-editing-and-deleting-annotations#other-object-label-actions),
so we recommend checking that out if you[']{dir="rtl"}re curious. For
now, let[']{dir="rtl"}s stick to the most useful info that may not be
immediately obvious:

When you stop working on a Label Entity, it is locked automatically.

Your Series must be in a currently open viewport tab in order for Jump
to Label to work.

If you have a Label Entity selected, you can mouse over the viewport and
use the corresponding hotkey to save yourself tons of clicks.

Label Actions Mastery

Taking a moment and committing one or two Label Actions hotkeys to
memory will save you hours while annotating. Complete the following
tasks to demonstrate your understanding of Label Actions.

Toggle highlighted mode for an Entity using the relevant hotkey

Scroll to an empty slice and use Jump to Label to return to your
annotation

Create a new Entity and then delete it

Bonus: the text for certain Label Actions changes depending on the
Entity state - can you find all of the changes?

Overlapping Segmentations

When you have a segmentation selected, the [[Masking
Panel]{.underline}](https://docs.redbrickai.com/annotation/visualization-and-masking#masking)
appears on the righthand side of the screen.

The [[Masking
Panel]{.underline}](https://docs.redbrickai.com/annotation/visualization-and-masking#masking)
consists of the following elements:

Editable Area dropdown

Modify Other Segments dropdown

Restrict by pixel intensity toggle (which we[']{dir="rtl"}re ignoring
for now)

In order to properly annotate this Necrosis, we[']{dir="rtl"}ll need an
understanding of the first two fields - Editable Area and Modify Other
Segments. Please see the following brief video for an overview of these
fields:

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/11/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Overlapping
Segmentations](https://www.loom.com/share/536fa33679814e2f909e4944b1c0f8ba?source=embed_watch_on_loom_cta)

2 min

97 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~2 min 18 sec~~

⚡️

2 min 53 sec

2 min 18 sec

1 min 55 sec

1 min 32 sec

1 min 21 sec

1 min 9 sec

55 sec

Your user agent does not support the HTML5 Video element.

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/11/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Overlapping
Segmentations](https://www.loom.com/share/536fa33679814e2f909e4944b1c0f8ba?source=embed_watch_on_loom_cta)

2 min

97 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~2 min 18 sec~~

⚡️

2 min 53 sec

2 min 18 sec

1 min 55 sec

1 min 32 sec

1 min 21 sec

1 min 9 sec

55 sec

If you prefer to read, here[']{dir="rtl"}s a text summary as well:

Editable Area: Everywhere allows you to annotate anywhere on the canvas,
and Inside all segments only allows you to annotate inside of an
existing segmentation.\
\
Modify Other Segments: Overlap allows you to paint on top of other
annotations, and Overwrite unlocked segments means that painting on top
of an existing annotation will delete the underlying annotation.

Demonstrate your understanding of overlapping segmentations by doing the
following:

Create a ["]{dir="rtl"}throw-away" Edema annotation anywhere on the
canvas

Create a Necrosis annotation inside of your ["]{dir="rtl"}throw-away"
Edema annotation

Hide the Necrosis label you just created - what do you see?

Enable Editable Area: Inside all segments and create a Necrosis
annotation inside of your ["]{dir="rtl"}throw-away" Edema annotation

Enable Editable Area: Inside all segments and create a Necrosis
annotation outside of your ["]{dir="rtl"}throw-away" Edema annotation -
does it work?

Enable Modify Other Segments: Overwrite unlocked segments and create a
Necrosis annotation inside of your ["]{dir="rtl"}throw-away" Edema
annotation

Hide the Necrosis label you just created - what do you see?

In certain cases, it[']{dir="rtl"}s extremely useful to cross-reference
a single scan modality with another.

RedBrick AI has two features that allow you to do so:

Intellisync allows you to synchronize multiple Series at once.

Label Mirroring allows you to visualize annotations on multiple Series
at once.

We[']{dir="rtl"}re going to combine these features for our Necrosis
workflow, but before that, let[']{dir="rtl"}s do the following:

Create a 2x1 Layout Tab

Put the Axial view of the FLAIR image in the lefthand viewport

Put the Axial view of the T1CE in the righthand viewport

Make sure both Series are centered (by pressing SPACE)

Highlight the Edema label (so it[']{dir="rtl"}s more visible)

The final result should look something like this:

![65af937f9590b831c4f9eaa6_Untitled
(4).png](extractions/11/images/media/image5.png){width="6.4998611111111115in"
height="3.889738626421697in"}

When all of that is done, let[']{dir="rtl"}s activate Intellisync and
Label Mirroring on these two Series.

You can find both of these settings by clicking on the hamburger menu in
the top right of a Series viewport.

![65af93ac6d2ef4bd97de2790_Untitled
(5).png](extractions/11/images/media/image6.png){width="6.4998611111111115in"
height="6.7658409886264215in"}

When using Intellisync, the ["]{dir="rtl"}host" Series will have a blue
upward-facing arrow! You can also mouse over this arrow to see which
Series is ["]{dir="rtl"}hosting" the mirrored labels.

Intellisync and Label Mirroring Mastery

These two features will be critical when annotating the Necrosis, so
let[']{dir="rtl"}s review briefly.

Complete the following tasks to demonstrate an understanding of
Intellisync and Label Mirroring:

Toggle Intellisync on and off on multiple Series using both the menu and
the corresponding hotkey

Mirror your Edema annotation so that it displays on another Series

Use both Intellisync and Label Mirroring to see how your Edema
annotation displays on other scans

Annotating Necrosis within the Edema

It[']{dir="rtl"}s now time to pull together everything
you[']{dir="rtl"}ve learned!

Use all of your knowledge of the Annotation Tool[']{dir="rtl"}s features
to produce a full annotation of Necrosis within the Edema

Once you[']{dir="rtl"}re done, you will likely have something that looks
like this.

![65af9422f12662528ce14356_Untitled.gif](extractions/11/images/media/image4.gif){width="6.4998611111111115in"
height="3.7130457130358705in"}

Wrap-up and Additional Resources

Congratulations! You[']{dir="rtl"}ve made great progress on the road to
RedBrick mastery by making it all to the end of this use case. Pat
yourself on the back!

We wish you the best of luck in your annotation journey moving forward.
Don[']{dir="rtl"}t forget to reach out to us at
[[support@redbrickai.com]{.underline}](mailto:support@redbrickai.com)
with any questions or feedback!

If you[']{dir="rtl"}d like to learn more about the platform, please feel
free to consult the following resources:

[[RedBrick AI Documentation]{.underline}](https://docs.redbrickai.com/)

[[RedBrick AI SDK
Reference]{.underline}](https://redbrick-sdk.readthedocs.io/en/stable/sdk.html)

[[RedBrick AI YouTube
Channel]{.underline}](https://youtube.com/@redbrickai)

[[RedBrick AI Changelog]{.underline}](https://changelog.redbrickai.com/)

[[RedBrick AI Blog]{.underline}](https://blog.redbrickai.com/)
