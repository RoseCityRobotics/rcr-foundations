# Publishing these guides as a GitHub wiki

GitHub wikis are separate repositories (`your-repo.wiki.git`) that live
alongside the main code repository.  You can mirror the Markdown files
in this `rcr‑foundations` repo into a wiki so that students can browse
them directly on GitHub without navigating the repository tree.

## Steps to publish the wiki

1. **Create or clone the wiki repo.**  Go to your repository on
   GitHub and click the **Wiki** tab.  If no wiki exists, click
   **Create the first page** to initialise it.  Then clone the wiki:

   ```bash
   git clone git@github.com:ROSE-CITY-ROBOTICS/rcr-foundations.wiki.git wiki
   cd wiki
   ```

2. **Copy Markdown files.**  Copy the relevant `.md` files from
   `../rcr-foundations` into the `wiki` directory.  You can organise
   them into folders or a flat structure.  For example:

   ```bash
   cp -r ../rcr-foundations/unix ../rcr-foundations/git \
         ../rcr-foundations/rpi-ubuntu \
         ../rcr-foundations/microcontrollers \
         ../rcr-foundations/docker \
         ../rcr-foundations/imaging \
         ../rcr-foundations/windows \
         ../rcr-foundations/dev-tools .
   ```

3. **Commit and push.**  In the `wiki` directory:

   ```bash
   git add -A
   git commit -m "docs: import RCR foundations guides"
   git push
   ```

GitHub will render the wiki automatically.  You can edit pages
directly in the wiki repo or continue to sync updates from the
`rcr‑foundations` repo.

## Tips

* Create a `Home.md` page in the wiki to provide an overview and link
  to the subpages.  You can borrow the structure of the main
  `README.md`.
* Avoid extremely long pages in the wiki; break content into smaller
  files for better navigation.

By mirroring the guides into a wiki, you provide easy top‑level
navigation for students while maintaining version control and pull
request workflows in the main repository.