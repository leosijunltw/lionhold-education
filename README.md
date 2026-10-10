# Lionhold Education website

A dependency-free static website for Lionhold Education, part of the Lionhold group. It shares its design with the Lionhold Capital website.

Pages: Home (`index.html`), LionholdAI, the AI platform (`platform.html`), University application support (`university.html`), School consulting (`schools.html`), Job application support (`jobs.html`), About us (`about.html`) and Meet the team (`team.html`).

## Preview locally

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy to Cloudflare Pages

1. In Cloudflare, open **Workers & Pages → Create → Pages → Connect to Git**.
2. Select this repository.
3. Leave the **build command** blank and set the **build output directory** to `/` (or leave it empty).
4. Deploy. Cloudflare gives you a free `*.pages.dev` address, and you can attach your own domain afterwards under **Custom domains**.

## Pictures and videos

See [MEDIA.md](MEDIA.md). The site currently uses placeholder images and videos; replace files in `assets/` with the same names.

## Before launch

- **Contact email:** every page currently uses `info@lionholdcapital.com`. Search the repo for it and swap in an education address when you have one.
- **Company details:** add your registered company name, address and any required legal notices or privacy policy.
- **Khmer name:** the logo is an open book with the name written in Khmer text ("ឡាយអិនហូលដ៍" is copied from the Capital logo; "អប់រំ" for Education is my choice). Have a Khmer speaker confirm the wording. To change it, edit the `brand-text` spans in each page.
- **Team roles:** the Meet the team page is copied from Lionhold Capital. Update titles if they differ at Lionhold Education.
- **AI platform status:** the site says the platform is "In development". Update the wording when it launches.

## Files

- `styles.css`: the shared Lionhold design (from the Capital site).
- `education.css`: Lionhold Education additions (logo, dropdown menus, AI platform preview, status pill, card links).
- `script.js`: menu, scroll effects and footer year.
