---
layout: post
title: Working with the Google Cloud 
categories: [general]
tags: [noneYet]
description: ""
permalink: /google-cloud
---

# Table of Contents
1. [Accessing the Cloud Shell](#cloudshell)
2. [Copying the Google Cloud image to your Compute Instance](#copyimage)
3. [Checking the status of the image](#statusimage)
4. [Creating the Google Cloud Instance](#createimage)
5. [Select a zone](#zone)
6. [Editing the Cloud Instance](#editinstance)
7. [Allow HTTP traffic](#httptraffic)
8. [Running the Cloud Instance](#runcloud)

## Accessing the Cloud Shell <a name="cloudshell"></a>

Your first step would be to log in to [Google Cloud Platform](https://console.cloud.google.com)
with your Google account (create one if you don't already have one). 

Once logged in, you will want to click on the `Activate Google Cloud Shell`
icon on the top right of the page (which looks like: **[>_ ]**).

## Copying the Google Cloud image to your Compute Instance <a name="copyimage"></a>

Enter the following command to create an instance with the saved image (it may take a few minutes): 

```
gcloud compute images create biostats2 --source-uri gs://cunysph-biostat/bios2-ima
ge.tar.gz
```

The image file is about `1 GB` large and can take quite some time to transfer
an create the image on your Cloud Platform. 

### Checking the status of the image <a name="statusimage"></a>

Once created, you can check to see if the image is ready for use with the command: 

```
gcloud compute images describe biostats2
```

You should see `status: READY` in the output

## Creating the Google Cloud Instance <a name="createimage"></a>

Now you're ready to create a computing instance with the image: 

```
gcloud compute instancees create bios2-instance --image biostats2
```

### Select a zone <a name="zone"></a>

Select a zone in `us-east1` by entering the numeric choice (from 11 to 13)

### Editing the Cloud Instance <a name="editinstance"></a>

In the web browser, select `VM instances` under the `Compute Engine` and find
your `bios2-instance`. 

Click on `bios2-instance` and then `EDIT` the instance at the top menu. 

#### Allow HTTP traffic <a name="httptraffic"></a>

Select the square button under **Firewall** for `Allow HTTP traffic` and click 
`SAVE` at the bottom. 

## Running the Cloud Instance <a name="runcloud"></a>

Now, under **External IP**, click on the IP address for your instance. 

You can now log in to the RStudio interface using the credentials `cunybiostat`
for both username and password. 

