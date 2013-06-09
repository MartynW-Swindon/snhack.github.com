snhack.github.com
=================

__Note:  master branch is overwritten during compilation.__

This site is built with [octopress] and requires a ruby installation to render the [source branch] to master.

[octopress]: http://octopress.org/docs
[octopress documentation]: http://octopress.org/docs/setup/
[source branch]: https://github.com/snhack/snhack.github.com/tree/source
[fork this repo]: https://github.com/snhack/snhack.github.com/fork_select
[pull request]: https://github.com/snhack/snhack.github.com/pulls

### Super minimal way to add a post

> If you're submitting a standard text or markdown post, you can follow this section to add your text using the github site.

Browse to the [source/_posts] folder within the source branch of this repo.

[source/_posts]: https://github.com/snhack/snhack.github.com/tree/source/source/_posts

Use github's web interface to [create a new file], [naming it] according to the pattern: ``YYYY-MM-DD-url-safe-title.md``.  This will prompt Github to create a fork of this project for you to work in.

[create a new file]: https://github.com/blog/1327-creating-files-on-github
[naming it]: https://github.com/blog/1436-moving-and-renaming-files-on-github

Add [suitable yaml] front matter followed by your content as plain text, as shown in [this example post] \([preview]).  Optionally use \*simple\* [markdown formatting] such as headers, italics and links.  There are [various tools] available to preview standard markdown.

[this example post]: https://raw.github.com/snhack/snhack.github.com/source/source/_posts/_examples/2012-11-06-example-post.md
[preview]: https://github.com/snhack/snhack.github.com/blob/source/source/_posts/_examples/2012-11-06-example-post.md

Commit the new file using the button labelled "Propose New File", Github will automatically prompt you to submit a pull request to this repo.  Ensure the base branch is set to 'source', review the changes (especially the "Files Changed" tab), then hit "Send pull request".

[suitable yaml]: http://octopress.org/docs/blogging
[markdown formatting]: http://daringfireball.net/projects/markdown/basics
[various tools]: http://daringfireball.net/projects/markdown/dingus



### Install and Build Locally

> This section explains how to install the entire site and related tools to your local machine.
> To simply submit a post, commit a standard text/markdown file as explained above.

When using the extensions provided by octopress or jekyll, or making changes to the site, you should install octopress so you can preview your content before submission.

[Fork this repo], then clone your fork's **source branch** locally.

	git clone -b source git@github.com:<yourusername>/snhack.github.com.git snhack
	cd snhack
	ruby --version  		# Should report Ruby 1.9.3


Install dependencies, but do not run ``rake install`` (it's been done already).

	gem install bundler rake
	rbenv rehash			# Only needed with rbenv
	bundle install

If you have any problems, see the [octopress documentation] for more info on installing ruby and other dependencies.



### Adding Content or Changes

> Regular users of git can submit content or changes to the site using the standard pull request workflow as shown below.

Creating a new topic branch is preferred, especially for changes to the site's source (including templates and styles).

	git checkout -b myfix

Make your changes, such as a [new post or page] in [markdown] format.

	rake new_post["Zombie Ninjas Attack"]

	# Edit the new post created by rake
	nano source/_posts/2011-07-03-zombie-ninjas-attack.md

[new post or page]: http://octopress.org/docs/blogging
[markdown]: http://daringfireball.net/projects/markdown


Generate and preview your changes locally at ``http://localhost:4000``.

	rake generate   # Generates posts and pages into the public directory
	rake preview	# Watches, and mounts a webserver at http://localhost:4000


Commit changes, then push them to your fork.

	git commit -am "That fix, for the thing."
	git push origin myfix

Submit a [pull request] to this repo (use the button shown on your new branch).

Once your changes are accepted, an admin will need to generate the site using ``rake deploy`` before they become live.
