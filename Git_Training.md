---
author: Akarsh Verma

---

<h1 id="learn-git-..--v-1.0">Learn Git … !! V 1.0</h1>
<p>Hi! I’m will be your guide to learn <strong>Git</strong>.</p>
<blockquote>
<p>To keep things simple we will use the command line to execute Git commands.</p>
</blockquote>
<p><a href="%5Bhttps://git-scm.com/%5D(https://git-scm.com/)">Git</a> is a version-control system for tracking changes in source code during software development. It is designed for coordinating work among programmers.</p>
<p><a href="%5Bhttps://github.com/%5D(https://github.com/)">Github</a> brings together the world’s largest community of developers to discover, share, and build better software.</p>
<p>We will use <a href="%5Bhttps://github.com/%5D(https://github.com/)">Github</a> as the platform to practice our learning.</p>
<p>&lt;img src=“<a href="https://git-scm.com/images/branching-illustration@2x.png">https://git-scm.com/images/branching-illustration@2x.png</a>” width=“500” height=“300” "/&gt;</p>
<h4 id="lets-begin-by-creating-a-local-repository-execute-the-command-in-a-cell">Let’s Begin by Creating a Local Repository (Execute the command in a Cell)</h4>
<pre><code>&gt; Git init

Initialized empty Git repository in D:/git_training/.git/
</code></pre>
<blockquote>
<p>The Exclamation Mark ensures that the command is executed as a Terminal Command. The Output shows that we have created a local Empty git repository.</p>
</blockquote>
<p>We should be able to evaluate the status of the created repository using the “Status” command</p>
<pre><code>&gt; Git status
</code></pre>
<p>This would allow us to check the current status of our Repository at any point in time.</p>
<pre><code>On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
</code></pre>
<p>Let’s add a New File to the Folder called “<strong>hello.txt</strong>” which has a sample text inside it.</p>
<p>Execute the following to see if Git has started tracking changes.</p>
<pre><code>&gt; Git Status
</code></pre>
<p>The Output should be something similar to this.</p>
<pre><code>On branch master

No commits yet

Untracked files:
  (use "git add &lt;file&gt;..." to include in what will be committed)
        hello.txt

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
</table><p><strong>Git Branch</strong> - A <strong>branch in Git</strong> is simply a lightweight movable pointer to one of these commits. The default <strong>branch</strong> name in <strong>Git</strong> is <strong>master</strong>. As you initially make commits, you’re given a master <strong>branch</strong> that points to the last commit you made. Every time you commit, it moves forward automatically.<br>
<br></p>
<p><strong>Git Commit</strong> - <strong>Commits are</strong> created with the <em>git commit</em> command to capture the state of a project at that point in time.</p>
<p>Effectively we are trying to achieve the following workflow:<br>
<br></p>
<img src="https://www.nobledesktop.com/image/gitresources/git-branches-merge.png">
<p>We will now add the files that are currently untracked.</p>
<pre><code>&gt; Git add . 
&gt; Git status
</code></pre>
<p>We will be adding the un-tracked listed above in our repository. Notice the “dot” at the end. This is to select all the files. Alternatively, file names can be specified.</p>
<pre><code>On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached &lt;file&gt;..." to unstage)
        new file:   hello.txt
</code></pre>
<p>The status has not changed to <strong>No Commits</strong> which specifies that changes are yet to be committed to the branch master.</p>
<p>Before we start committing Git needs to know who we are in order to maintain a name and email ID along with the commits. Execute the following before making a commit.</p>
<pre><code>&gt; git config --global user.email "you@example.com"
&gt; git config --global user.name "Your Name"
</code></pre>
<p>Now, let’s <strong>Commit</strong></p>
<pre><code>&gt; Git commit -m "Initial Commit"
</code></pre>
<p>The <strong>hyphen m</strong> specifies the comment that should be added to commit. Consider it like a change log that a user can maintain.</p>
<pre><code>[master (root-commit) 4bf0552] Initial Commit
 1 file changed, 2 insertions(+)
 create mode 100644 hello.txt
</code></pre>
<p>The following message confirms that 1 files was changed with 2 lines added into Git version system. Furthermore we can track <strong>Git Status</strong> which we have already learnt.</p>
<h2 id="branching">Branching</h2>
<p>Branching is just a natural way to manage and maintain individual code in isolation and merge when ready to the master. This approach allows multiple people to work on same code base and realize the changes once everyone is ready. This is naturally collaborative.</p>
<p><strong>Git Branch</strong> is a command to allow to work with branches.</p>
<pre><code>&gt; Git branch --create dev
</code></pre>
<p>This creates a new branch called <strong>dev</strong>. This is just a name and can be anything. Usually branch names are tied to environments or feature or people depending on the Team’s agreement.  We can easily see the branches we have.</p>
<pre><code>&gt; Git branch --list

  dev
* master
  qa
</code></pre>
<p>I have crated two branches dev &amp; qa apart from master. The * denotes the current branch under selection/operation.</p>
<p>Let’s do a <strong>Checkout</strong></p>
<p>The <strong>git checkout</strong> command lets you navigate between the <strong>branches</strong> created by <strong>git branch</strong> . Checking out a <strong>branch</strong> updates the files in the working directory to match the version stored in that <strong>branch</strong>, and it tells <strong>Git</strong> to record all new commits on that <strong>branch</strong>.</p>
<pre><code>&gt; git checkout dev
Switched to branch 'dev'
</code></pre>
<p>We can validate anytime the working branch using the <strong>Status</strong> command.</p>
<pre><code>&gt; Git Status
On branch dev
nothing to commit, working tree clean
</code></pre>
<p>Let’s make an edit to the file and check the status again.</p>
<pre><code>On branch dev
Changes not staged for commit:
  (use "git add &lt;file&gt;..." to update what will be committed)
  (use "git restore &lt;file&gt;..." to discard changes in working directory)
        modified:   hello.txt

no changes added to commit (use "git add" and/or "git commit -a")
</code></pre>
<p>While this specifies that  change was made to the file and it is not committed, It is difficult to understand the exact changes that were made.</p>
<p><strong>Git Diff</strong> to the rescue.</p>
<p><strong>git diff</strong> is a multi-use <strong>Git</strong> command that when executed runs a <strong>diff</strong> function on <strong>Git</strong> data sources. These data sources can be commits, branches, files and more. … The <strong>git diff</strong> command is often used along with <strong>git</strong> status and <strong>git</strong> log to analyze the current state of a <strong>Git</strong> repo.</p>
<p>Before we see that we should ensure that we have performed the following operations to the current branch.</p>
<ol>
<li>Git Add - To ensure the changes are added to the current branch.</li>
<li>Git Commit - To Ensure that changes are saved to the current branch.</li>
</ol>
<p>We can execute the <strong>diff</strong> command now.</p>
<pre><code>&gt; git diff dev..master

diff --git a/hello.txt b/hello.txt
index 21f10ab..3e23ae4 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1,2 +1,2 @@
-hello there.
-How are you Doing ?
+
+hello
</code></pre>
<p>This describes every addition and deletion operation with the modified record.<br>
&gt; 1. Created an Empty Git Repository and added a file to it to track.</p>
<blockquote>
<p>To Summarize our actions so far. We have achieved the following :<br>
2. Created different branches<br>
3. On Branch <strong>dev</strong> we have edited and saved the information that was changed.<br>
4. The changes were evaluated using <strong>Git Diff</strong> command.</p>
</blockquote>
<p>Our Master is still behind by an update compared to <strong>dev</strong> branch. A handy command to use is <strong>Git Log</strong></p>
<p>The <strong>Git Log</strong> tool allows you to view information about previous commits that have occurred in a project. The simplest version of the <strong>log</strong> command shows the commits that lead up to the state of the currently checked out branch. These commits are shown in reverse chronological order (the most recent commits first).</p>
<p>Let’s fire it up.</p>
<pre><code>&gt; git log

commit 2b1ab39870ed9eb38c47a34c6dd08cb5b4a92c09 (HEAD -&gt; dev)
Author: Akarsh &lt;akarsh.verma@live.in&gt;
Date:   Sun Jun 14 01:34:49 2020 +0530

    Update

commit 4bf055215f054e1e553bd9aa727cee237bd3eaff (qa, master)
Author: Akarsh &lt;akarsh.verma@live.in&gt;
Date:   Sun Jun 14 01:07:43 2020 +0530

    Initial Commit
</code></pre>

