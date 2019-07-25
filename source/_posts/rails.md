---
title: Rails Active Storage
date: 2019-07-25 15:25:16
tags:
---

New ways to handle file uploads, share credentials with your team, set up Content Security Policy, even start your application—we are looking at what’s new in Rails 5.2 and focus on Active Storage with a step-by-step introduction to the new framework.

Even though we did not get it as a promised New Year present and were just told to wait another month for the official release, Rails 5.2 was assigned RC1 status and is now considered stable. So we might as well start unwrapping! You can install Rails 5.2 today by running gem install rails --prerelease.

Out of all new shiny things that the last major update before Rails 6 brings, Active Storage stands out the most. For the first time in Rails history, we get a built-in solution for handling file uploads in our projects. According to DHH, Active Storage was extracted from Basecamp 3, so it claims to be a framework “born from production”.

We will talk about Active Storage first, and then, if you bear with 

### With things attached

Disclaimer: we will not go into comparing Active Storage with existing solutions, be it CarrierWave, Paperclip or Shrine, but rather try to make a beginner-friendly introduction to the framework as we get to know it ourselves.

Enabling Active Storage in your application starts with a Rake task: running rails active_storage:install in the command line will add a new migration to your db/migrate folder. Once executed, it creates two tables that Active Storage needs to deliver on its promises: active_storage_attachments and active_storage_blobs. Here is what they do, according to framework’s README:

Blob stands for “binary large object”, as our attachments are, in essence, large binary files. active_storage_blobs does not put the binary into a database, but tracks its location, along with information on file’s size, content type, and metadata.

“Active Storage uses polymorphic associations via the Attachment join model, which then connects to the actual Blob. Blob models store attachment metadata (filename, content-type, etc.), and their identifier key in the storage service.”

This approach sets Active Storage apart from the competition. Paperclip, Carrierwave, Shrine—all these popular solutions require you to add columns to existing models. The only widely used gem that relies on virtual attributes to handle attachments is Attachinary, a ridiculously easy-to-use proprietary solution that is locked to Cloudinary’s storage.

Support for other cloud services can be implemented by extending ActiveStorage::Service class.

Active Storage, it seems, takes the same direction, but allows you to choose where to keep your files: be it your hardware or popular cloud providers. Amazon S3, Google Cloud Storage, and Microsoft Azure Storage are supported out of the box.