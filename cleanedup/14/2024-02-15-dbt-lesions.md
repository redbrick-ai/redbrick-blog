---
title: "Guide: Lesion Detection in Mammography, DBT, and Breast MRI"
date: "2024-02-15"
category: "Clinical"
excerpt: "A comprehensive guide on using RedBrick AI for multi-modality breast imaging analysis. Learn specialized workflows for mammogram hanging protocols, DBT lesion detection using cineloop, and 3D tumor detection in breast MRI with synchronized viewing capabilities."
author: "Shivam Sharma"
thumbnail: "./image1.png"
---

Lesion detection in mammography, DBT and breast MRI

Shivam Sharma

February 15, 2024

In this guide we will focus on RedBrick AI's features for
breast imaging. We'll walk through three projects focusing
on different modalities, and the special features the platform has for
efficient viewing and annotation.

## Mammography

In this project, we will annotate the left and right standard mammogram
views — Cranial Caudal (CC) and Medial Lateral Oblique (MLO). Each
study will include two timepoints for the same patient. We will focus on
importing the data and correctly configuring hanging protocols.

### Preparing & uploading the data

We will use publicly sourced data that is hosted by RedBrick AI and
publicly accessible. Data accessible through public URLs can easily
imported into RedBrick AI using an [Items List](https://docs.redbrickai.com/importing-data/import-cloud-data/creating-an-items-list).

*Download mammography [JSON file here](https://drive.google.com/file/d/1ipmJyYN9FhPLjSUa2hK62IKE80pHsbCr/view?usp=drive_link). This file follows the RedBrick AI [items list format](https://docs.redbrickai.com/importing-data/import-cloud-data/creating-an-items-list).*

The items list has three tasks with data in the following format:
```json
{
	// Unique name for the task
	"name": "0025a5dc99fd5c742026f0b2b030d3e9-4",

	// Each task has 8 series, 4 for each timepoint
	"series": [
		// Timepoint 1
		{
			"name": "R-CC",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/fcf12c2803ba8dc564bf1287c0c97d9a.dicom"
		},
		{
			"name": "L-CC",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/451562831387e2822923204cf8f0873e.dicom"
		},
		{
			"name": "R-MLO",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/47c8858666bcce92bcbd57974b5ce522.dicom"
		},
		{
			"name": "L-MLO",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/2ddfad7286c2b016931ceccd1e2c7bbc.dicom"
		},

		// Timepoint 2
		{
			"name": "R-CC-2",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/fcf12c2803ba8dc564bf1287c0c97d9a.dicom"
		},
		{
			"name": "L-CC-2",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/451562831387e2822923204cf8f0873e.dicom"
		},
		{
			"name": "R-MLO-2",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/47c8858666bcce92bcbd57974b5ce522.dicom"
		},
		{
			"name": "L-MLO-2",
			"items": "https://datasets.redbrickai.com/mammography/0025a5dc99fd5c742026f0b2b030d3e9/2ddfad7286c2b016931ceccd1e2c7bbc.dicom"
		}
	]
}
```


To import this data within your [RedBrick AI project](https://docs.redbrickai.com/projects/get-started-with-a-project), simply upload the JSON file through Upload Data → External Storage → Public.

![](./import_data.mp4)

### Hanging the mammograms

Hanging protocols are crucial for effectively viewing mammograms. Our goal is to view all eight mammograms in the study simultaneously, by arranging them in as shown in the diagram below. Furthermore, we want to apply a default windowing that's different for the CC & MLO views.

![65cda8534db29f47bae56125_Untitled (15).png](extractions/14/images/media/image1.png)

We can add a hanging protocol to our project to automatically set up the viewer in this way. You can write a custom Javascript function to define your hanging protocol. Defining the hanging protocol with JS code gives you almost unlimited functionality in implementing custom hanging
protocol logic.

*Read through hanging protocols [documentation here](https://docs.redbrickai.com/annotation-and-viewer/viewer-basics/custom-hanging-protocol).*

1. First, set the dimensions of the viewer to 4 columns and 2 rows. This is done using the `setDimensions(4, 2)` function in the hanging protocol.
2. We need to place each image in the correct viewport. Refer to the order of the images in the JSON files from the preparing & uploading data section. The series list contains images in this order: R-CC, L-CC, R-MLO, L-MLO, R-CC-2, L-CC-2, R-MLO-2, L-MLO-2. RedBrick AI populates the viewer from the top left to the right. R-CC will occupy the first viewport on the top left, and L-MLO-2 will fill the last available viewport on the bottom right.
3. Now that the views are properly positioned, we can add default windowing to the CC & MLO views. The `setWindowing(seriesIndex, level, width)`  function from the hanging protocol can be used to apply this default windowing. The seriesIndex starts at 0 and corresponds with the position of the series in the `series:[]` object in the items file, as mentioned in the previous section.
	1. CC views have seriesIndex --- 0,1,4,5.
	2. MLO views have seriesIndex --- 2,3,6,7.

By combining the points above, we get the following hanging protocols
script.

```js
setDimensions(4,2);

// Set CC windowing
[0,1,4,5].forEach(index => setWindowing(index, 1500, 760));

// Set MLO windowing
[2,3,6,7].forEach(index => setWindowing(index, 1600, 1500));
```


Add this hanging protocol script to your project settings:

![](./hangingprotocol.mp4)

Now all tasks will appear with the correct configuration enabling efficient viewing and annotation!

## Digital Breast Tomosynthesis tumor detection

Digital breast tomosynthesis (DBT) is an advanced form of breast imaging that is gaining popularity, especially in cancer detection. In this project, we'll annotate lesions using 2D bounding boxes slice by slice.

### Taxonomy set up

While creating a project, make sure to add a 2D bounding box titled
"lesion" so we can annotate lesions slice by slice.

![](./taxonomy.mp4)

*Please refer to our documentation on [project setup](https://docs.redbrickai.com/projects/get-started-with-a-project) and [taxonomies](https://docs.redbrickai.com/projects/taxonomies) for detailed information.*

### Importing data

As in the previous section, we\'ll utilize a public items file to import the DBT data.

*You can download the public DBT [items JSON file here](https://drive.google.com/file/d/1e-PjHa8uwkh4vDXKBAa7utoEVoeu7C9Q/view?usp=drive_link).*

To import the public JSON file into a project, navigate to Import Data → External Storage → Public.

### 2D bounding box annotation using cineloop

Cineloop is a useful feature on RedBrick AI that allows you to view your 3D volumes as a sequence of 2D frames, similar to a video. This is particularly beneficial for performing annotations like 2D bounding box slice-by-slice annotation. To activate Cineloop, right-click on a viewport and select "cineloop". This will reveal a "timeline" at the bottom of the viewport.

With the Cineloop timeline visible, you can utilize the interpolation features, as demonstrated in the video below, to effectively annotate with bounding boxes across the 3D volume.

![](./cineloop.mp4)

‍
## Breast MRI 3D tumor detection

Breast MRI is often used as a supplementary tool to mammography or ultrasound, especially in diagnosing and evaluating breast cancer. In this project, we will use two different weighted MRI series per study to annotate lesions using cuboid bounding boxes.

### Add cuboid to project taxonomy

While creating a project, make sure to add a 3D bounding box titled "lesion" (i.e., a cuboid type) so we can annotate lesions.

![](./taxonomy2.mp4)

*Please refer to our documentation on [project setup](https://docs.redbrickai.com/projects/get-started-with-a-project) and [taxonomies](https://docs.redbrickai.com/projects/taxonomies) for detailed information.*

### Importing data

As in the previous section, we'll utilize a public items file to import the breast MRI data.

*You can download the public MRI [items JSON file here](https://drive.google.com/file/d/1sYDVdaCUTn1JYeUeWadjURzZhqVHtaBI/view?usp=drive_link).*

To import the public JSON file into a project, navigate to Import Data → External Storage → Public. Similar to the section on Mammography, each entry in the items list has a the following format:
```json
{
    "name": "L and R CC",
    // Each task (study) has two series
    "series": [
        {
            "items": [
                "https://datasets.redbrickai.com/trials/breast-tomo/rcc.dcm"
            ],
            "name": "RCC"
        },
        {
            "items": [
                "https://datasets.redbrickai.com/trials/breast-tomo/lcc.dcm"
            ],
            "name": "LCC"
        }
    ],
    // You can include meta data along with each task.
    // This meta data will be visible on the annotation viewer.
    "metaData": {
        "Name": "Study-level metadata",
        "Description": "You can upload text and links here (or at the Series level) to provide additional guidance for your annotators!",
        "Link": "https://docs.redbrickai.com/annotation/overview#task-level-and-series-level-metadata"
    }
}
```


### 3D bounding box using intellisync and label mirroring

First, we\'re going to annotate the lesion on the initial MRI series in MPR mode. Then, using intellisync, we\'ll synchronize the view, including the scroll position, pan, and zoom level. This enables us to project the cuboid on the remaining series for synchronized viewing. As a result, we can examine the annotations on different weighted MRI scans for more precise annotations.

## Annotating initial series in MPR mode

![](./boundingbox.mp4)

### Synchronized viewing with Intellisync and label mirroring

*Read more about [Intellisync](https://docs.redbrickai.com/annotation-and-viewer/viewer-basics/intellisync) and [label mirroring](https://docs.redbrickai.com/annotation-and-viewer/viewer-basics/annotation-mirroring) in our documentation.*
