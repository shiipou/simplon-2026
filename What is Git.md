## What is Git System
[<font color="#ff0000">Git</font>](https://git-scm.com/) is a free and Open Source <mark style="background:#fff88f">versioning</mark> system. It allows <mark style="background:#d3f8b6">agility</mark>, <mark style="background:#d3f8b6">organisation</mark> when working, and easy <mark style="background:#d3f8b6">monitoring</mark> of project's files versions, issues, and updates

## How to use it
There is many alternatives to use Git system such as :
- [Git](https://git-scm.com/)
- [GitHub](https://github.com/)
- GitLab
- ...

Some are using <mark style="background:rgba(240, 200, 0, 0.2)">web or applications interfaces <font color="#8064a2">(GUI)</font></mark>, <mark style="background:rgba(240, 200, 0, 0.2)">bash commands <font color="#8064a2">(CLI)</font></mark> and can often be embedded (as <mark style="background:rgba(240, 200, 0, 0.2)">plugins</mark> or other) inside an IDE/Editor for easier access an time gain.

These alternatives are nearly all the time available on both Solaris based (Linux, MacOS, ...) and Windows based systems.

## Git Architecture

### Git branch structure :
A project is divided of one or more branches :

- It is at first composed of a <mark style="background:#fff88f">main/origin branch</mark> which represents the <mark style="background:#fff88f">start of the project</mark>
- Then, projects can be divided by what we call "<mark style="background:#fff88f">branches</mark>", which allows to <mark style="background:#fff88f">edit the file in parallel of the main project</mark> without submitting changes which can cause several issues

### Git file transit structure :
Git architecture seems hard at first sight but is actually kind of easy to understand. It is composed of :
- <mark style="background:#b1ffff">A repository (repo)</mark> hosted on distant servers
- <mark style="background:#b1ffff">A stash</mark> (can be translatted as "réserve" in french) : it contains in middle informations to avoid unintentionnal problems of versioning
- A <mark style="background:#b1ffff">local workspace</mark> where you can get files or send them from

## Git's conflicts gestion
Git allows users to manage conflicts easily, by keeping files in stash while users manages what changes to keep and to delete.
Branch are also used to avoid <font color="#d99694">"<font color="#d99694">spaghettis</font>"</font> and <mark style="background:rgba(205, 244, 105, 0.55)">keep origin branch clean</mark>, by using "branch squash" or "branch rebase" (do not use rebase if you're not sure of what you're doing !).

## [How git file transfer works](git_transfer_schema.canvas)