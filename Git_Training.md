---
author: Akarsh Verma

---

<h1 id="learn-git-from-jupyter-notebooks-">Learn Git from Jupyter Notebooks !!</h1>
<p>Hi! I’m will be your guide to learn <strong>Git</strong>.</p>
<blockquote>
<p>To keep things simple we will use the command line to execute Git commands.</p>
</blockquote>
<p><a href="%5Bhttps://git-scm.com/%5D(https://git-scm.com/)">Git</a> is a version-control system for tracking changes in source code during software development. It is designed for coordinating work among programmers.</p>
<p><a href="%5Bhttps://github.com/%5D(https://github.com/)">Github</a> brings together the world’s largest community of developers to discover, share, and build better software.</p>
<p>We will use <a href="%5Bhttps://github.com/%5D(https://github.com/)">Github</a> as the platform to practice our learning.</p>
<img src="https://git-scm.com/images/branching-illustration@2x.png" width="500" height="300">
<h4 id="lets-begin-by-creating-a-local-repository-execute-the-command-in-a-cell">Let’s Begin by Creating a Local Repository (Execute the command in a Cell)</h4>
<pre><code>Git init

Initialized empty Git repository in D:/git_training/.git/
</code></pre>
<blockquote>
<p>The Exclamation Mark ensures that the command is executed as a Terminal Command. The Output shows that we have created a local Empty git repository.</p>
</blockquote>
<p>We should be able to evaluate the status of the created repository using the “Status” command</p>
<pre><code>Git status
</code></pre>
<p>This would allow us to check the current status of our Repository at any point in time.</p>
<pre><code>On branch master
No commits yet

    Untracked files:
  (use "git add &lt;file&gt;..." to include in what will be committed)
	.ipynb_checkpoints/
	Untitled.ipynb

nothing added to commit but untracked files present (use "git add" to track)
</code></pre>
<p>This is very informational. Let us evaluate each of the messages before proceeding further.</p>

<table>
<thead>
<tr>
<th>Message</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>On branch master</td>
<td>We are currently working on master branch.</td>
</tr>
<tr>
<td>No commits yet</td>
<td>have not made any commits to the repository so far.</td>
</tr>
<tr>
<td>Untracked files</td>
<td>found some files which are listed below this              	message. This implies that Git was able to find some files which are part of the folder which Git is Tracking for changes.</td>
</tr>
</tbody>
</table><br>
<br>
<p><strong>Git Branch</strong> - A <strong>branch in Git</strong> is simply a lightweight movable pointer to one of these commits. The default <strong>branch</strong> name in <strong>Git</strong> is <strong>master</strong>. As you initially make commits, you’re given a master <strong>branch</strong> that points to the last commit you made. Every time you commit, it moves forward automatically.<br>
<br></p>
<p><strong>Git Commit</strong> - <strong>Commits are</strong> created with the <em>git commit</em> command to capture the state of a project at that point in time.</p>
<p>Effectively we are trying to achieve the following workflow:<br>
<br></p>
<img src="https://www.nobledesktop.com/image/gitresources/git-branches-merge.png">
<p>We will now add all the files that are currently untracked.</p>
<pre><code>Git add . 
Git status
</code></pre>
<p>We will be adding the un-tracked listed above in our repository. Notice the “dot” at the end. This is to select all the files. Alternatively, file names can be specified.</p>
<pre><code>On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached &lt;file&gt;..." to unstage)
	new file:   .ipynb_checkpoints/Untitled-checkpoint.ipynb
	new file:   Untitled.ipynb

Changes not staged for commit:
  (use "git add &lt;file&gt;..." to update what will be committed)
  (use "git restore &lt;file&gt;..." to discard changes in working directory)
	modified:   Untitled.ipynb
</code></pre>
<p>The status has not changed to <strong>No Commits</strong> which specifies that changes are yet to be committed to the branch master.</p>
<p>Before we start committing Git needs to know who we are in order to maintain a name and email ID along with the commits. Execute the following before making a commit.</p>
<pre><code>git config --global user.email "you@example.com"
git config --global user.name "Your Name"
</code></pre>
<p>Now, let’s <strong>Commit</strong></p>
<pre><code>Git commit -m "Initial Commit"
</code></pre>
<p>The <strong>hyphen m</strong> specifies the comment that should be added to commit. Consider it like a change log that a user can maintain.</p>
<pre><code>[master (root-commit) 8adb831] Initial Commit
 2 files changed, 113 insertions(+)
 create mode 100644 .ipynb_checkpoints/Untitled-checkpoint.ipynb
 create mode 100644 Untitled.ipynb
</code></pre>
<p>The following message confirms that 2 files were changed with 113 lines added into Git version system. Furthermore we can track <strong>Git Status</strong> which we have already learnt.</p>

