Segmentation of large organs in abdominal CT scans

Ben Stewart

January 23, 2024

Part I - Configuring your environment

For this walkthrough, we will be using scans from the Abdomen (Sample)
Project included with your RedBrick AI trial.

Throughout this document, you[']{dir="rtl"}ll find check boxes that you
can fill in after completing the associated task. For example:

Open a Task in the Abdomen (Sample) Project in RedBrick AI

Masking

You can apply pixel-based thresholding to any image or volume on
RedBrick to define a ["]{dir="rtl"}paintable" range when annotating.

For more information on the Masking Panel, check out our [[full
documentation]{.underline}](https://docs.redbrickai.com/annotation-and-viewer/visualization-and-masking#restrict-by-pixel-intensity).

To define your thresholding range:

Create a new segmentation in the left hand toolbar

Click the Restrict by pixel intensity toggle in the right hand Context
Panel

![Attachment.png](extractions/12/images/media/image1.png){width="0.2222222222222222in"
height="0.2222222222222222in"}

Adjust the slider as necessary to increase or decrease your paintable
range (i.e. the flashing blue regions of the canvas)

![Attachment.png](extractions/12/images/media/image1.png){width="0.2222222222222222in"
height="0.2222222222222222in"}

For annotating the Kidneys, try a range of 60-610!

Part II - Annotation

For Admins - setting a default thresholding range

If you[']{dir="rtl"}re familiar with DICOM and PACS viewers,
you[']{dir="rtl"}ve likely made use of [[Hanging
Protocols]{.underline}](https://docs.redbrickai.com/annotation-and-viewer/viewer-basics/custom-hanging-protocol#custom-hanging-protocol-format-reference),
and they[']{dir="rtl"}re also available on RedBrick AI!

setThresholding(0, 40, 610)

Head to Project Settings → Hanging Protocol and paste the above function
into the field to define a project-wide thresholding range:

Preview not available. No embeds API access.

[[Click here]{.underline}](https://share.redbrickai.com/0vfkYvXG) to
visit the page.

Annotating the kidneys

Let[']{dir="rtl"}s explore several ways to annotate the kidneys using
the Segmentation Toolkit.

3D Brush + Masking

When using Masking, you can[']{dir="rtl"}t paint outside of the flashing
blue regions of your canvas. We can combine this setting with the 3D
Brush to paint across slices very quickly, as demonstrated in the video
below.

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/12/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the kidney with the 3D Brush, 3D Hole Filling, & 3D Island
Tool](https://www.loom.com/share/ef143f1a096c4dcc9c5bed24a101273f?source=embed_watch_on_loom_cta)

1 min

15 views

2

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~1 min 4 sec~~

⚡️

1 min 20 sec

1 min 4 sec

53 sec

42 sec

37 sec

32 sec

25 sec

😮

James Morales

2

![Attachment.png](extractions/12/images/media/image1.png){width="0.2222222222222222in"
height="0.2222222222222222in"}

Thank you Ben! 🙏

+1 other comment

Your user agent does not support the HTML5 Video element.

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/12/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the kidney with the 3D Brush, 3D Hole Filling, & 3D Island
Tool](https://www.loom.com/share/ef143f1a096c4dcc9c5bed24a101273f?source=embed_watch_on_loom_cta)

1 min

15 views

2

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~1 min 4 sec~~

⚡️

1 min 20 sec

1 min 4 sec

53 sec

42 sec

37 sec

32 sec

25 sec

😮

James Morales

2

![Attachment.png](extractions/12/images/media/image1.png){width="0.2222222222222222in"
height="0.2222222222222222in"}

Thank you Ben! 🙏

+1 other comment

Flow Toolkit:

Masking Panel → Thresholding

3D Brush Tool

3D Hole Filling - to ensure no stray holes in the kidney annotation

3D Island Tool - to delete any stray voxels outside of the kidney

3D Contour Tool

Using the [[3D Contour
Tool]{.underline}](https://docs.redbrickai.com/annotation-and-viewer/segmentation/segmentation-tools#contour-tool)
doesn[']{dir="rtl"}t require the use of thresholding, so
we[']{dir="rtl"}re going to adopt a different approach for the left
kidney.

[[Smart Contour
Tool:]{.underline}](https://docs.redbrickai.com/annotation-and-viewer/segmentation/segmentation-tools#contour-tool)
hold CTRL+ALT (or CTRL+OPTION on MacOS) and hover over the boundary of a
structure to display the Smart Contour. Once you are satisfied with the
Contour, click LMB to create it or LMB+drag to smooth the Contour.

The 3D Contour Tool utilizes interpolation to create contours across a
defined range. See the diagram below:

![65af91118386fcd2d1e05a68_Untitled
(2).png](extractions/12/images/media/image2.png){width="6.4998611111111115in"
height="3.175980971128609in"}

Let[']{dir="rtl"}s get some labeling done - follow along in the
Annotation Tool!

create a second Entity for Kidneys

disable Restrict by pixel intensity (if you have it enabled)

scroll to the top or bottom of the un-annotated kidney

create a contour on a single slice

rasterize the single contour by clicking on Rasterize in the right hand
Context Panel (or using SHIFT+ENTER)

create a 3D contour using interpolation & rasterize it

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/12/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the kidney with 3D Contour
Tool](https://www.loom.com/share/1f4bd6f54993465bad57b575ea301858?source=embed_watch_on_loom_cta)

29 sec

9 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~29 sec~~

⚡️

37 sec

29 sec

24 sec

19 sec

17 sec

14 sec

11 sec

Your user agent does not support the HTML5 Video element.

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/12/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the kidney with 3D Contour
Tool](https://www.loom.com/share/1f4bd6f54993465bad57b575ea301858?source=embed_watch_on_loom_cta)

29 sec

9 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~29 sec~~

⚡️

37 sec

29 sec

24 sec

19 sec

17 sec

14 sec

11 sec

Flow Toolkit:

3D Contour Tool

3D Hole Filling - to ensure no stray holes in the kidney annotation

2D Adaptive Brush Tool - to ensure pixel-perfect cleanup after the
contours are done

3D F.A.S.T.

RedBrick AI also offers AI-assisted segmentation with our Fast Automated
Segmentation Tool, or
[[F.A.S.T.]{.underline}](https://www.notion.so/da3b77b233034b3fa0d0d4aacf97fc5b?pvs=21)

Like the 3D Contour Tool,
[[F.A.S.T.]{.underline}](https://www.notion.so/da3b77b233034b3fa0d0d4aacf97fc5b?pvs=21)
uses interpolation to allow you to annotate rapidly across a slice
range.

F.A.S.T. is enabled for all free trials, so let[']{dir="rtl"}s give it a
try.

select the Entity you want to segment (or create a new one)

use LMB to create a box around the Kidney

use LMB again to complete the box and activate F.A.S.T.

after the segmentation is generated, use LMB to supply F.A.S.T. with
positive feedback (i.e. ["]{dir="rtl"}annotate here")

after the segmentation is generated, use RMB to supply F.A.S.T. with
negative feedback (i.e. ["]{dir="rtl"}do not annotate here")

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/12/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the kidney with 3D
FAST](https://www.loom.com/share/e66b3e60dd17492bb807ea07980aab77?source=embed_watch_on_loom_cta)

31 sec

9 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~31 sec~~

⚡️

39 sec

31 sec

26 sec

20 sec

18 sec

15 sec

12 sec

Your user agent does not support the HTML5 Video element.

![19999708_5c432ed2985fd54450a37f1670fd669d_192.jpg](extractions/12/images/media/image1.jpeg){width="2.6666666666666665in"
height="2.6666666666666665in"}

[Annotating the kidney with 3D
FAST](https://www.loom.com/share/e66b3e60dd17492bb807ea07980aab77?source=embed_watch_on_loom_cta)

31 sec

9 views

0

0.8×

1×

1.2×

1.5×

1.7×

2×

2.5×

~~31 sec~~

⚡️

39 sec

31 sec

26 sec

20 sec

18 sec

15 sec

12 sec

Object Label Attributes

In some Projects, your administrators will ask you to assign extra data
attributes to certain Object Labels.

select one of your Kidney Entities and then look at the right hand
Context Panel

expand the Renal Masses field

![Attachment.png](extractions/12/images/media/image1.png){width="0.2222222222222222in"
height="0.2222222222222222in"}

Selecting one of these Attributes will map it to whichever Entity you
currently have selected, making it visible to your data / MLOps
colleagues upon export.

You can read more about Object Label Attributes in our official
documentation
[[here]{.underline}](https://docs.redbrickai.com/projects/taxonomies#object-label-attributes).

Annotating the liver & pancreas

It[']{dir="rtl"}s time to put everything together and define a flow that
works best for you.

annotate the Liver using any of the above methods (or a combination of
them)

annotate the Pancreas using any of the above methods (or a combination
of them)

Part III - Export

Semantic Export

This Project and walkthrough are making use of semantic annotation, and
those curious can read about the different types of annotation
[[here]{.underline}](https://docs.redbrickai.com/annotation-and-viewer/segmentation/instance-vs.-semantic).

RedBrick AI offers a special type of [[data
export]{.underline}](https://docs.redbrickai.com/python-sdk/sdk-overview/exporting-annotations)
(called Semantic Export) that can greatly simplify your
team[']{dir="rtl"}s post-processing efforts and provide peace of mind
for quality control purposes.

Light Reading:

[[SDK Overview
(Python)]{.underline}](https://docs.redbrickai.com/python-sdk/sdk-overview)

[[General Export Information
(Python)]{.underline}](https://docs.redbrickai.com/python-sdk/sdk-overview/exporting-annotations)

[[Full Python API
Reference]{.underline}](https://redbrick-sdk.readthedocs.io/en/stable/sdk.html)

Whether you[']{dir="rtl"}re working in Python or the CLI, you can make
use of Semantic Export to ensure that you will always have only one
annotation per Object Label.

Python

project = redbrick.get_project(org_id, project_id, api_key, url)

project.**export**.export_tasks(semantic_mask=True)

CLI

\# in local directory

redbrick export \--semantic

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
