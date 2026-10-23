# Emortalics — studio website

A fast, static website for Emortalics: home page, game pages, a playable browser version of Deadstock,
YouTube, devlog, newsletter sign-up and privacy policy. No build tools, no server: it runs on GitHub Pages for free.

## Put it online with GitHub Pages (once)

1. Make a free account on **github.com**.
2. Create a new repository named exactly **`YOURUSERNAME.github.io`** (use your GitHub username).
   This makes the site live at `https://YOURUSERNAME.github.io`. Set it to **Public**.
3. On the repository page click **Add file → Upload files**, then drag in **everything inside this folder**
   (`index.html`, `assets`, `games`, `devlog`, `privacy`, `404.html`, `.nojekyll`). Click **Commit changes**.
   *(Tip: the `.nojekyll` file is hidden on Mac/Windows. If it doesn't upload, it's fine; it only matters if you add files starting with `_`.)*
4. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
5. Wait a minute or two and open `https://YOURUSERNAME.github.io`.

Easier way to keep it updated: install **GitHub Desktop**, clone the repository, copy files in, and press **Commit** then **Push**.

### Your own domain (optional)
Buy a domain (for example `emortalics.com`, about $10–15 a year) from Namecheap, Porkbun or Cloudflare.
In **Settings → Pages → Custom domain** type it in and follow GitHub's DNS instructions. Tick **Enforce HTTPS**.

## Add the playable game

1. In Unity, build the WebGL version (the same build you upload to itch.io).
2. Copy what's **inside** the build folder (`index.html`, `Build`, `TemplateData`) into
   `games/deadstock/play/build/`, replacing the placeholder text file.
3. Upload/push. The **Play** page now runs the game. (The build's decompression fallback, already set up by
   *Emortalics → Prepare WebGL Build*, is what lets it run on GitHub Pages.)
   GitHub has a 100 MB per-file limit; Deadstock is far below that.

## Everyday edits: `assets/js/content.js`

Everything you'll change often is in that one file:

- **Links**: `email`, your itch.io page (`games[0].links.itch`), Google Play later, and `socials`.
  Empty `""` hides a button.
- **YouTube**: put your channel URL in `youtube.channel`, and video IDs in `youtube.videos`
  (the ID is the part after `watch?v=`), e.g. `videos: ["abc123XYZ", "def456"]`.
- **Newsletter**: make a free account at **buttondown.com**, then set
  `newsletterAction: "https://buttondown.com/api/emails/embed-subscribe/YOURNAME"`.
  (Mailchimp or ConvertKit also work: paste their form's *action* URL.)
- **Devlog**: add a new block at the top of `posts`. `body` is simple HTML (`<p>`, `<h2>`, `<ul><li>`, `<img src="...">`).
  Put post images in `assets/img/` and refer to them like `assets/img/my-picture.png`.
- **A new game**: add a block to `games` and copy the `games/deadstock/` folder to `games/your-game/`,
  then change the text and pictures in its `index.html`.

## Screenshots
Replace the pictures in `assets/img/deadstock/` with real F12 screenshots from the game any time (keep the
same file names, or update the names in the pages).

## Privacy policy
`privacy/` holds Deadstock's policy. Fill in the highlighted [brackets] before you publish on Google Play,
then paste `https://YOURUSERNAME.github.io/privacy/` into the Play Console.
