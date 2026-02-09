After you finish a project and want it to be deployed on github:
1.
Allow dist to be committed
By default, Git ignores the dist folder, but for this specific deployment method, we need to upload it.

Open the file named .gitignore.
Look for a line that says dist or dist/.
Delete that line (or put a # in front of it to comment it out).
Save the file.
2.
Run the build command:
********
npm run build
*******
3.
git add .
git commit -m "Build project for deployment"
git push origin main
**********
4.
This command takes the dist folder and pushes only that folder to the gh-pages branch.
****
git subtree push --prefix dist origin gh-pages
****

What to expect next:
The command might take a few seconds.
Once it says "success" or "pushed to gh-pages", go to your GitHub Repository settings on the website.
Go to Pages.
Ensure the source is set to Branch: gh-pages -> Folder: / (root).
Wait about 2 minutes, and your site should be live!
