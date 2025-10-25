# GOPODC / cldtech — Instrucțiuni pentru adăugarea fotografiilor

Acest README explică rapid cum să încarci fotografiile în branch-ul `site-preview` ca să apară pe site.

Fișiere recomandate
- Nume recomandate: `hero.jpg`, `p1.jpg`, `p2.jpg`
- Formate: .jpg sau .png (evită .hdr)
- Dimensiune recomandată: până la 4 MB fiecare; redimensionează pentru web dacă e nevoie.

Opțiunea A — Încărcare rapidă (GitHub web UI)
1. Accesează: https://github.com/GOPODC/cldtech
2. Selectează branch: "site-preview" (butonul Branch)
3. Click: Add file → Upload files
4. Alege fișierele (ex.: hero.jpg, p1.jpg, p2.jpg)
5. La "Commit changes" selectează "Commit directly to the site-preview branch" → Commit changes

Opțiunea B — Folosind Git (CLI)
1. git clone https://github.com/GOPODC/cldtech.git
2. cd cldtech
3. git checkout site-preview
4. mkdir -p assets
5. cp /cale/catre/hero.jpg assets/hero.jpg
   cp /cale/catre/p1.jpg assets/p1.jpg
   cp /cale/catre/p2.jpg assets/p2.jpg
6. git add assets/hero.jpg assets/p1.jpg assets/p2.jpg
7. git commit -m "Add site assets images"
8. git push origin site-preview

Actualizarea index.html pentru a afișa imaginile
- Hero/banner (în secțiunea .hero):
  <img src="assets/hero.jpg" alt="Banner" class="hero-img">

- Proiecte (în lista Proiecte):
  <li><img src="assets/p1.jpg" alt="Proiect 1" class="thumb"> Proiect 1 — descriere scurtă</li>
  <li><img src="assets/p2.jpg" alt="Proiect 2" class="thumb"> Proiect 2 — descriere scurtă</li>

Fragmente CSS recomandate (pune în css/styles.css):
  .hero-img { max-width:100%; height:auto; border-radius:8px; margin-top:1rem; display:block; margin-left:auto; margin-right:auto; }
  .thumb { width:120px; height:auto; border-radius:6px; margin-right:0.75rem; vertical-align:middle; }

Publicarea site-ului (GitHub Pages)
- Poți publica direct din branch `site-preview` sau poți crea un branch `gh-pages` și publica din el.
- Pași (web): Settings → Pages → Source → selectează branch (`site-preview` sau `gh-pages`) → Save
- După activare, linkul va arăta: https://GOPODC.github.io/cldtech

Dacă dorești, eu pot:
- crea branch `gh-pages` din `site-preview` și activa Pages (îmi permiți să modific Settings → Pages?)
- fuziona PR #1 în `main`

Dacă vrei instrucțiuni suplimentare sau să fac eu publicarea, răspunde: "Publică gh-pages" sau "Fuzionează în main".