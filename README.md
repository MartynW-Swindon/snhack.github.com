## snhack.github.com

__Note:  master branch is overwritten during compilation.__

Please see the [INSTALL](INSTALL.md) file for full details on how to build and
preview this site locally.


### Super minimal way to add a post

> Use this workflow when submitting a blog post using standard text or markdown.

Load the [source/_posts] folder of the source branch, then use the [new file] icon above its listing.  [[show]][new-file]

*Github will automatically create a copy of this project (a '[fork]') for your own use.*

[new-file]: http://swindon.hackspace.org.uk/images/help/1-new-file.png
[commit-file]: http://swindon.hackspace.org.uk/images/help/2-commit-file.png
[send-pull-request]: http://swindon.hackspace.org.uk/images/help/3-send-pull-request.png

[source/_posts]: https://github.com/snhack/snhack.github.com/tree/source/source/_posts
[fork]: https://help.github.com/articles/fork-a-repo
[pull request]: https://help.github.com/articles/using-pull-requests

Name the new file using your preferred post date and title,
according to the pattern: `YYYY-MM-DD-url-safe-title.md`.  [[show]][commit-file]

[new file]: https://github.com/blog/1327-creating-files-on-github
[naming it]: https://github.com/blog/1436-moving-and-renaming-files-on-github

Enter basic post metadata, followed by your content as plain text or [markdown].
Here's a [template] and some [syntax examples].

[template]: https://raw.github.com/snhack/snhack.github.com/source/source/_posts/_examples/2012-01-01-template.md
[syntax examples]: https://github.com/snhack/snhack.github.com/tree/source/source/_posts/_examples

Use the `Propose New File` button to commit the post to a new branch in your own fork.

You will be prompted to create a [pull request] - this will submit your new post to this
repo.

Check the file changes displayed are as expected, add any relevant info, and then hit
`Send Pull Request`.  [[show]][send-pull-request]

[post metadata]: http://octopress.org/docs/blogging
[markdown basics]: http://daringfireball.net/projects/markdown/basics
[markdown]: http://daringfireball.net/projects/markdown/dingus


### Notes on Pull Requests

Once you have sent a [pull request] an admin will need to build the site locally, check
it renders acceptably, and then deploy your content to the live site.

You can view the progress of your pull request in its [discussion thread].
Notifications will normally be sent by email to those active or mentioned
in the thread, as well as those watching either the thread or the related repo.

Additional commits made to the same branch (named with the 'patch' prefix by default)
will automatically be added to the pull request.

Check the [fork] and [pull request] help pages for more info.

[discussion thread]: https://github.com/snhack/snhack.github.com/issues
[github help]: https://help.github.com


### Uploading Images

The [new file] icon on the github website only supports text files. You can reference
images hosted elsewhere, but it's sometimes best to upload images to the site itself.

If you're familiar with `git`, you can commit images into a new folder located within
[source/_posts/_images] and named to match your post: `YYYY-MM-DD-name-of-post`.

[source/_posts/_images]: https://github.com/snhack/snhack.github.com/tree/source/source/_posts/_images

An easier option is to attach images to the [discussion thread] of your newly created
pull request, an admin can then commit them into the correct folder.

Use `{{ page.url }}` in your post to automatically reference the correct folder.

    ![MyImage]({{ page.url }}/MyImageFile.jpg)

