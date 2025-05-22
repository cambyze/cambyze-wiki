# Performance aspects
![Cambyze Logo](cambyze_icon.png)

Technical best practices and performance recommendations for Cambyze applications.

## Table of Contents
- [Using java.util.stream to manipulate collections](#using-java.util.stream-to-manipulate-collections)

---


Jump to

- Confluence navigation

[Confluence navigation](https://cambyze.atlassian.net/wiki/spaces/Cambyze/pages/3932161/Performance+aspects#AkTopNav)

- Side navigation

[Side navigation](https://cambyze.atlassian.net/wiki/spaces/Cambyze/pages/3932161/Performance+aspects#AkSideNavigation)

- Page

[Page](https://cambyze.atlassian.net/wiki/spaces/Cambyze/pages/3932161/Performance+aspects#AkMainContent)

[restrictions.empty](https://cambyze.atlassian.net/wiki/spaces/Cambyze/pages/3932161/Performance+aspects)

[Jira links](https://cambyze.atlassian.net/wiki/spaces/Cambyze/pages/3932161/Performance+aspects)

- 

![image](Performance aspects - Cambyze - Confluence_files/3b9de68c-85a4-40dd-b98a-b06ac812b4fb)

- Cambyze

![](Performance aspects - Cambyze - Confluence_files/712020_1b39b6a8-c15c-499f-8b80-e86d3861e7bd)

[Cambyze](https://cambyze.atlassian.net/wiki/people/712020:1b39b6a8-c15c-499f-8b80-e86d3861e7bd?ref=confluence&src=profilecard)

[Feb 05, 2025](https://cambyze.atlassian.net/wiki/pages/diffpagesbyversion.action?pageId=3932161&selectedPageVersions=5&selectedPageVersions=6)

This page deals with some ways to increase Java performance


## Using java.util.stream to manipulate collections

See the relativeJava documentation

[Java documentation](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/stream/Stream.html)

Example with the use ofparallelStreamto manipule a cashflow as aLinkedHashMap<LocalDate, BigDecimal>

![thumbs up](Performance aspects - Cambyze - Confluence_files/1f44d.png)

![clapping hands](Performance aspects - Cambyze - Confluence_files/1f44f.png)

![party popper](Performance aspects - Cambyze - Confluence_files/1f389.png)