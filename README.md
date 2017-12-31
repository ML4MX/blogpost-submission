### blog posts submission repository

This is the submission repository for the [Machine Learning For Mexico Blog](https://ml4mx.github.io/website/blog/).


### How to submit a blog post?

1. Create a [github](https://github.com) account

2. [Fork](https://help.github.com/articles/fork-a-repo/) the [blogpost submission](https://github.com/ML4MX/BlogPost-submission) repository

3. Clone this new repository into your desktop environment

   ```
   $ git clone https://github.com/YOUR-USERNAME/blogpost-submission
   ```

4. Create a branch (the branch name should be author names separated with dashes)

   ```
   $ git checkout -b AUTHOR1-AUTHOR2
   ```

5. Add your code & article (see [author guidelines](https://rescience.github.io/write)) and commit your changes:

   ```
   $ git commit -a -m "Some comment"
   ```

6. [Push](https://help.github.com/articles/pushing-to-a-remote/) to github

   ```
   $ git push origin AUTHOR1-AUTHOR2
   ```

7. Issue a [pull request](https://help.github.com/articles/using-pull-requests/) (PR) to https://github.com/ML4MX/blogpost-submission/pulls with title containing author(s) name and follow the template that will appear once you opened the pull request:

  ```
  **Miguel P Xochicale**

  Dear Editors,

  I request a review for the following blog post:

  ### Original article

  **Title: Why GitHub and how to use it?**  
  **Author(s): Miguel P Xochicale**  
  **Keywords**: Github  
  **Repository**:  https://github.com/mxochicale/blogpost-submission-whygithub/


  ### Potential reviewers
  <!-- If you know potential reviewers, you can tell us here --> 
  <!-- You can look at http://rescience.github.io/board for the --> 
  <!-- list of registered reviewers (but you can propose others) --> 

  --- 

  **EDITOR**

  * [ ] Editor acknowledgement ( [@mxochicale](https://github.com/mxochicale) )
  * [ ] Reviewer 1 ( [@omarcr](https://github.com/omarcr) [@ekhar666](https://github.com/ekhar666)  )
  * [ ] Reviewer 2 (  [@danielggm](https://github.com/danielggm)   [@ortuno](https://github.com/ortuno) )
  * [ ] Review 1 decision [accept/reject]
  * [ ] Review 2 decision [accept/reject]
  * [ ] Editor decision [accept/reject]
  ```

8. You can suggest reviewers from [editorial board](https://ml4mx.github.io/website/members.html).

9. Answer questions and requests made in the PR conversation page.


### References

This repository is inspired by [ReScience-submission](https://github.com/ReScience/ReScience-submission).
