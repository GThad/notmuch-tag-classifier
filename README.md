[Notmuch](https://notmuchmail.org/) is an excellent email system for efficient email storage and powerful querying. To provide better email organization, it makes use of "tags." Notmuch only provides the means to tag emails, but leaves the actual tagging to the user. Some users have manually created rule-based scripts to automate this tagging, however updating these rules can become tedious.

**This repository houses code that full automates the tagging process after learning from one's existing database of tagged emails.**

During the initialization step, the following steps are taken:

1. Load emails from the given Notmuch database.
2. Transform email data into a form suitible for training.
3. Train model.

After the model is trained and is called from Notmuch configuration files, it will automatically tag new emails. It is likely the model will incorrectly tag or fail to tag some emails. If the user fixes these, the model will take note of the difference and learn incrementally.