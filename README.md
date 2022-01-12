# Instructor Guide for FarmData2-For190VC-Activities

The FarmData2-For190VC-Activites repository is a diconnected fork of [FarmData2](https://github.com/DickinsonCollege/FarmData2) created for class activites that introduce Free and Open Source Software (FOSS) collaboration models using git and GitHub with a branching workflow.  

## Activities

There is a sequence of 4 activites that cover the following topics:

1. FOSS Community and Collaboration: [[Slides](https://dickinson-comp190.github.io/website/materials/07-S-VCI-CommCollab.pptx) | [Activity](https://dickinson-comp190.github.io/website/materials/07-A-VCI-CommCollab.docx)]
   * An introduction to FOSS communites, how they collaborate using version control (e.g. git) and repository hosting (e.g. GitHub).
   * Includes practice with the issue tracker, forking, cloning and setting an upstream remote.
2. Upstreaming in FOSS [[Slides](https://dickinson-comp190.github.io/website/materials/08-S-VCII-Upstreaming.pptx) | [Activity](https://dickinson-comp190.github.io/website/materials/08-A-VCII-Upstreaming.docx)]
   * Introduces feature branches, commits and pull requests as part of a basic branching workflow.
   * Includes practice with creating and switching branches, staging and committing changes, pushing to origin and submitting pull requests. 
3. Staying Synchronized [[Slides](https://dickinson-comp190.github.io/website/materials/09-S-VCIII-SynchWithUpstream.pptx) | [Activity](https://dickinson-comp190.github.io/website/materials/09-A-VCIII-SynchWithUpstream.docx)]
   * Looks at how asynchronous collaboration results in local repository being out of synch with the upstream and how to resolve this by pulling automatically merged changes.
   * Includes having code merged into upstream main, practice with pulling changes from upstream main, pushing to origin, deleting feature branches.
4. Resolving Merge Conflicts [[Slides](https://dickinson-comp190.github.io/website/materials/10-S-VCIV-MergeConflicts.pptx) | [Activity](https://dickinson-comp190.github.io/website/materials/10-A-VCIV-MergeConflicts.docx)]
   * Introduces conflicting changes, how they lead to merge conflicts, how they can be resolved.
   * Includes practice with merging main into a feature branch, merge conflict representation, using a merge tool and updating a pull request.

### Using this Repository

The following steps outline how to to get setup and then how to use this repostory with the above activities.

#### Set Up

1. Fork this repository to the location where you want students to find it.
   * Note: One fork will support up to 26 students. If you have more than 26 students you will need to have multiple repositories.
3. Optionally rename your fork to something appropraite to your course/assignments.
4. Optionally delete the "Instructor" branch from your fork.
5. Copy the issues from this repository into your fork:
   1. Fork the [git-hub-issues-import](https://github.com/IQAndreas/github-issues-import) repository.
   2. Edit the `config.ini` to include:
      1. Your username
      2. A GitHub PAT with access to your fork as the password.
      3. The `braughtg/FarmData2-For190VC-Activities` as the source repository.
      4. Your fork as the target repository.
   c. Run `python3 gh-issues-import.py --open`
      * Sometimes this will give an authentication error after some number of issues are copied.  If it does, rerun it using specific issue numbers so that all issues are copied. E.g. `python3 gh-issues-import.py --issues 21 22 23 24` to copy issues 21, 22, 23 and 24.

#### FOSS Community and Collaboration

In this activity students will fork and clone the repository and will claim a `190-round1` issue in the issue tracker.  The activity instructs students to claim an issue by commenting on it and that issues will be assigned to the first student to comment on each issue.  The instructor should assign issues to the student in the issue tracker.  There are enough `190-round1` issues for 26 students.

#### Upstreaming in FOSS

In this activity students will make changes to address the issue that they were assigned. They will then make a pull request to the upstream (i.e. your fork).  All of the `190-round1` issues have been selected so as not to create any conflicts.  Thus, the students will see that their pull requests can be merged automatically. The pull requests can be merged as they come in, but it has been an effective demonstration to merge them in class when this assignment is complete.

#### Staying Synchronized ####

After the pull requests from the prior assignment have been merged, the `main` branches in the students' local and origin repositories will be out of synch with the upstream `main`.  They will pull the changes from upstream `main` and, if all goes well, they will be fast-forward merged.  They will the push the their local `main` branch, with the updates, to their origin.  This brings the `main` branches of their repositories into synch with the upstream.

After synchronizing with the upstream, the students go on to claim an `190-round2` issue in the issue tracker.  There are only 4 `190-round2` issues, so multiple students will be working on each one.

At the point when most or all students have synchronized with the upstream, make a pull request for the `addRound2Conflicts` branch in your fork and merge it. This branch creates conflicts with each of the changes requested in a `190-round2` issue.  So, when the students ultimately create a pull request for their `190-round2` issue it will not be able to be merged automatically.  

It has also been effective to wait to merged the `addRound2Conflicts` breanch at the start of the next class meeting. In that case all student will see that their pull request can be merged automatially when they create it.  However, once the `addRound2Conflicts` branch is merged they will all change to not being able to be merged automatically.  Doing this in class allowed for the concurrent changes made by the pull reqeust to be illustrated live.

#### Resolving Merge Conflicts

In this activity students synchronize with the upstream to get the conflicting changes that were merged by the `addRound2Conflicts` branch. They then merge those changes into their feature branch creating a conflict.  They use a merge tool to resolve the conflict and then push the chnges to their origin to update their pull request.  Their goal is to have their pull requests updated so that they again are able to be merged automatically.  There is ultimately no need to merge these pull requests.

Inevitably some students will be behind on their work and will complete their sync with upstream after you have merged the `addRound2Conflicts` branch.  In these cases, their pull requests will not create a conflict to be resolved.  These students should pull the `mergeConflictPractice` branch and create a pull request for it.  That branch contains conflicts with those introduced in the `addRound2Conflicts` branch.  So they can then complete the activity using the `mergeConflictPractice` branch as it it were their original feature branch. Students not in this situation, but who would like additional practice can also pull the `mergeConflictPractice` branch.
