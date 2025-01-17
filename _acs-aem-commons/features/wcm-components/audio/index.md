---
layout: acs-aem-commons_feature
title: Audio Component
description: An HTML5 audio component and related workflow process
date: 2013-08-10
redirect_from: /acs-aem-commons/features/audio.html
feature-tags: component-dev components
tags: aemcs-incompatible
initial-release: 1.0.0
---

## Purpose

Provide an HTML5 audio component, similar to the HTML5 video component.

## Overview

Similar to the AEM HTML5 video component, audio files added to the DAM are transcoded into formats supported by HTML5, currently mp3 and OGG Vorbis, by FFMPEG.

## How to Use

* Edit the DAM Update Asset Workflow model
* Add a Process Step using the "Encode Audio" process.
* For the Process Arguments, provide "profile:ogghq,profile:mp3hq" and check the Handler Advance checkbox.
* Save the Workflow model

![Audio Component - Workflow Dialog](images/workflow-dialog.png)

* Drop the Audio component into your page, either from the Sidekick or the Audio Content Finder tab.

## Profiles

Like the HTML5 video support in AEM, audio support is based on profiles. Two profiles are included - "mp3hq" and "ogghq". If you need/want additional profiles, edit them just like you would a video profile.

If you create additional profiles, you will need to add them both in the workflow model and in the design dialog of the audio component.
