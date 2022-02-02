---
layout: default
title: Unified Search
parent: Pozi Server
grand_parent: Administrator Guide
---

# Unified Search

The Unified Search is a general purpose search utility designed to handle common search workflows that typical users might have. There is no limit to the number of datasets that can be configured in the search. However, the more that is added, the more potential for the search results of less useful features to crowd out the more important results.

The Unified Search doesn't support wildcards. However the index can be configured to take into account some variations if we can anticipate what the user might type in. (For instance, users searching for a crown allotment can start their query with 'CA' because the parcel search has been configured to anticipate this.) If there is a particular search that would require a wildcard, please let me know which dataset is affected and provide an example of what the user might type in.
## Configuration

The listed file names will indicate what is currently configured for searching. (Files that contain configurations for non-spatial data sources are prefixed with zzz to force them to the bottom because the spatial ones need to be be processed first.)
