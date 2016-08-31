---
layout: post
title: Working with the Google Cloud 
categories: [general]
tags: [noneYet]
description: ""
permalink: /google-cloud
---

# Table of Contents
1. [Accessing the Cloud Shell](#Accessing the Cloud Shell)
2. [Copying the Google Cloud image to your Compute Instance](#Copying the Google Cloud image to your Compute Instance)
3. [Checking the status of the image](#Checking the status of the image)
4. [Creating the Google Cloud Instance](#Creating the Google Cloud Instance)
5. [Select a zone](#Select a zone)
6. [Editing the Cloud Instance](#Editing the Cloud Instance)
7. [Allow HTTP traffic](#Allow HTTP traffic)
8. [Running the Cloud Instance](#Running the Cloud Instance)

## Accessing the Cloud Shell

Your first step would be to log in to [Google Cloud Platform](https://console.cloud.google.com)
with your Google account (create one if you don't already have one). 

Once logged in, you will want to click on the `Activate Google Cloud Shell`
icon on the top right of the page (which looks like: **[>_ ]**).

## Copying the Google Cloud image to your Compute Instance

Enter the following command to create an instance with the saved image (it may take a few minutes): 

```
gcloud compute images create biostats2 --source-uri gs://cunysph-biostat/bios2-ima
ge.tar.gz
```

The image file is about `1 GB` large and can take quite some time to transfer
an create the image on your Cloud Platform. 

### Checking the status of the image

Once created, you can check to see if the image is ready for use with the command: 

```
gcloud compute images describe biostats2
```

You should see `status: READY` in the output

## Creating the Google Cloud Instance

Now you're ready to create a computing instance with the image: 

```
gcloud compute instancees create bios2-instance --image biostats2
```

### Select a zone

Select a zone in `us-east1` by entering the numeric choice (from 11 to 13)

### Editing the Cloud Instance

In the web browser, select `VM instances` under the `Compute Engine` and find
your `bios2-instance`. 

Click on `bios2-instance` and then `EDIT` the instance at the top menu. 

#### Allow HTTP traffic

Select the square button under **Firewall** for `Allow HTTP traffic` and click 
`SAVE` at the bottom. 

## Running the Cloud Instance

Now, under **External IP**, click on the IP address for your instance. 

You can now log in to the RStudio interface using the credentials `cunybiostat`
for both username and password. 

