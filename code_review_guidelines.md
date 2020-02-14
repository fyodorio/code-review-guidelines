# [Team Name] Front-End Code Review Guidelines

1. Terms
    1. **PR** - Pull Request
    1. **CR** - Code Review
    1. **Requester (Reviewee)** - the person who creates pull request
    1. **Reviewer** - the person who reviews pull request being added to reviewers list
    1. **Team** – [Team Name] Front End Developers Team (Front End Chapter)
    1. **PO** – Product Owner (Vertical Team Lead)
2. Prerequisites
    1. Team's [Code Style Guide](https://google.github.io/styleguide/jsguide.html)
    1. Team's GitFlow [Rules](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) and [Best Practices](https://www.git-tower.com/learn/git/ebook/en/command-line/appendix/best-practices)
    1. Team's [Repository Name] Repository Documentation
3. TL;DR

    > Code Quality is a collective responsibility of the whole Team, and we need to establish constructive communication among the team members to achieve the highest productivity rate and stable Front End development flow.

4. Purpose
    1. Support mutual team respect and build healthy team relationships
        1. Emphasize the value of code reviews as not just the feedback but the interaction between the team members
        2. Facilitate camaraderie, trust, learning, and innovation
        3. Establish team responsibility for broken code
        4. Avoid a culture of fear among the reviewees
        5. Focus on what is best for the Team
    2. Maintain high code quality
    3. Reduce technical debt
    4. Prevent PR-induced bugs
        1. Caused by breaking code of the other team members
        2. Caused by producing potential merge conflicts
    5. Make building new features dominate over fixing bugs
5. General PR creation rules
    1. Make smaller PRs
        1. Opposite - slows the review process and lessens the number of active reviewers
        2. Decompose the initial task (and JIRA issue) if necessary
        3. Create additional tasks (JIRA issues) on the way if necessary
    2. If the feature is big
        1. Make a long-living big-feature branch
        2. Make a PR with [WIP] prefix
        3. Create separate granular PRs to the big-feature [WIP] branch
        4. Document approved sub-PRs along the way at [WIP] PR comments
    3. Make sure branch name contains at least short task description, not only its ID and type prefix
    4. Make sure commit messages speak for themselves
        1. Avoid message duplication
        2. Add the second paragraph if needed
    5. Make sure you follow the default GitFlow [branching model](https://nvie.com/img/git-model@2x.png)
6. Specific PR creation rules
    1. Read the feature description thoroughly to check if everything is implemented.
    2. Run the code and use it as the end user would. Double-check the requested feature's description.
    3. Check if the code follows the Team's Code Style Guide.
    4. Provide a descriptive title and useful description
        1. Screenshots and other visual aids are very helpful (if applicable)
    5. Mind the code ownership
        1. Add author for new component (_see [JSDOC documentation](https://jsdoc.app/tags-author.html)_)
        2. Notify the author for existent component
        3. If no authorship provided, use `git blame` for a specific file if not sure who's the author
    6. Merge the latest target branch code or rebase to it before creating the PR
    7. Re-build the code to make sure it has no build-time errors
    8. Make sure you've run the test suite, and all tests have successfully passes
    9. Self-review the diff before finishing PR creation
    10. Add QA engineers to reviewers list if necessary (bugfix, hotfix – required), ask your vertical Team's PO in case of any doubts
    11. Note if the PR can be merged by another developer, after receiving the necessary number of approvals, or if it's strongly prohibited
7. CR requesting and notifications
    1. In general, you don't need to additionally notify the Team about newly created PR. Automated notifications about new PR's and PR comments are provided for potential Reviewers in BitBucket's top bar and dedicated Slack channel
    2. You _can_ notify the Team about newly created PR additionally in dedicated Team's Slack channel (as well as about the comments to already existing PRs to attract additional attention to them)
    3. You _should_ notify the Team in dedicated Team's Slack channel about the important PRs that need specific attention (architectural changes and major code refactoring) or cover a lot of shared/core code, as well as about PRs of big-feature branches
8. CR flow rules
    1. Don't skip CR
        1. CR is not a chore; it's a team collaboration and a paid learning
        2. Investing 0.5 - 1 day per week into CR (= Code Quality) is fine
        3. Don't think that your review is not important - fresh view on a problem is always useful
    2. Provide CR _before PR is merged_
    3. Provide CR of important PRs _after PR is merged_ if you've missed it, and notify the Requester about the comments (if any) in Slack direct message
    4. Be friendly
        1. Don't underestimate the time and efforts your teammate invested in the PR
        2. Provide positive feedback (though it doesn't mean you should agree with whatever the person says)
        3. Phrase your review comments humbly and encouragingly
        4. At the very least, prepend your remarks with a "please";
        5. Consider framing your comments as a question, "Have you considered doing X in Y way?";
        6. If you hesitate that your feedback might be truly subjective, take a moment to ask, "Could you explain this part to me?";
        7. Explain the reasoning for your comment, if needed
    5. Be strict and thorough
        1. In case of any doubts - checkout to the PR'ed branch and build it
        2. Make update for the PR yourself if it does make sense, and the PR author doesn't mind or make a new PR with an update into the PR'ed branch
        3. Don't hesitate to block the PR if there are any doubts on code quality
    6. PR blocking
        1. Applying `Needs work` tag
            1. Mark PR as `Needs work` if you see any potential issue in provided code, have reasoned argument for alternative implementation, or suggest an important improvement for it.
            2. Be prepared to provide additional feedback and meet with Requester in person to discuss the details.
        2. Declining PR
            1. Decline PR only if there are severe violations of these Guidelines, Front End Team Code Style Guide, or GitFlow branching Rules. In other cases, prefer tagging the PR as `Needs work`.
            2. Notify the Requester directly that you're going to decline the PR (or did that already) and point him/her to the explanation.
            3. Provide your detailed feedback in PR comments for either case
9. CR feedback reaction and response
    1. Don't take it personally. The review is of the code, _not yourself_.
    2. Knowledge sharing is not an insult.
    3. It's always better to fail fast and fix fast.
    4. Respond to all the reviewers' comments (and fix corresponding issues if needed) ASAP.
    5. Be grateful for the Reviewer's suggestions. ("Good call. I'll make that change.")
10. CR deadlines
    1. General rule - PR should be waiting for peer reviews at least 24 hours
    2. If you make a PR at Friday, waiting time should be prolongated by 48 hours (72 total)
    3. Expand the PR's lifespan if it needs special attention
    4. Tight deadline conditions and prioritized business needs
        1. If PR is intended to fix a major `release` or `develop` branch issue, it should be announced, and such PR should be reviewed and merged ASAP
        2. If any problem hasn't been addressed and the PR needs to be accepted ASAP, describe it in comments and _create new JIRA tickets_ for remaining problems
            1. As Reviewer, emphasize the necessity of creating such new JIRA tickets to _avoid technical debt accumulation_ in comments during CR
11. Resolving merge conflicts
    1. Avoid default IDE/GUI suggestions without thorough code inspection
    2. Contact the code owner or the parallel Requester to identify the right way to resolve the conflict in case of any doubts
12. Final steps
    1. Once you had received feedback and addressed all issues, merge and close the PR, and remove the branch (if possible)
    2. Use "merge commit" strategy (`--no-ff`) to avoid losing information about the historical existence of a feature branch, and group together all commits that together added the feature
