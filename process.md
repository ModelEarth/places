# State and Zip Code File Generation

Each state file will probably be 5 to 20 MB (since the source file is 383.4 MB).

We'll generate the SQLite and .csv files daily for both zip codes and states.

We'll filter files for free client-side by [hosting timelines on Github Pages using SQLite](https://phiresky.github.io/blog/2021/hosting-sqlite-databases-on-github-pages/).

Here are the steps for installing the SQLite blog sample on your computer. The "blog" repo has an example of filtering timeline data in a browser.


## SQLite blog sample install

We recommend upgrading your OS before starting if your current version is more than 2 months old.

(1) Update to the latest version of Next and React.
And download the React DevTools for a better development experience:
[https://reactjs.org/link/react-devtools](https://reactjs.org/link/react-devtools)

	npm install next@latest react@latest react-dom@latest
	npm install -g react-devtools

---

(2) Clone our fork from: [https://github.com/localsite/blog](https://github.com/localsite/blog)
(Use the green "Code" button and open with Github Desktop to download.)

In our fork, Nextjs is migrated to the new version which uses RUST.

---

(3) Run these 4 commands in the blog folder (These are from the blog folder readme):

	yarn posts
	yarn dev
	yarn build
	yarn commit

---

(4) If you get an error with the "yarn dev" command, to resolve "SWC Failed to Load", include "--force" based on: https://nextjs.org/docs/messages/failed-loading-swc and run these 3 commands

	npm install --force
	npm audit fix --force
	yarn install

Hit return during "yarn install". (Entering an * didn't work.)

<!-- This is fixed now
5. Two errors  currently need to be resolved:

A. postprocess.sh Transformation error (Missing semicolon.
B. Transformation error (Topic reference is used, but the pipelineOperator plugin was not passed a "proposal": "hack" or "smart" option.
-->


## Local Sample of SQLite Blog

Once the steps are completed, you should see the following page:
https://phiresky.github.io/blog/2021/hosting-sqlite-databases-on-github-pages/


On your local computer by going here:
[http://localhost:3000/blog/2021/hosting-sqlite-databases-on-github-pages/](http://localhost:3000/blog/2021/hosting-sqlite-databases-on-github-pages/)

And you can view a list of all the blog posts at [localhost:3000/blog/](http://localhost:3000/blog/)


### Additional notes

Let Loren know if you used any of the following and we can move into steps above:

Ran to update pandoc. You may need to upgrade your OS and brew.

Install latest pandoc
https://github.com/jgm/pandoc/releases/latestpandoc --version

The following command may reveal that pandoc resides in the Anaconda folder.

	which pandoc

That seems to be okay. Ran (but no change to pandoc version in the Anaconda folder.)

conda update -n base anacondaYou may need to include --force when running this:git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow

brew update
brew upgrade
brew install pandoc


### Fixes applied in our Fork of the "blog" repo

Fixed nextjs link error.  Invalid <Link> with <a> child. Please remove <a> or use <Link legacyBehavior>

	npx @next/codemod new-link --force


Here's a Python script to [import .csv files into SQLite](https://github.com/phiresky/world-development-indicators-sqlite/).

We'll move the text above to a different page once we finish the steps.
<br><br>
