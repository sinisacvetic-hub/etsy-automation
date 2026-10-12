# Etsy Planner Automation — početni projekat

Ovo je početni projekat za web-aplikaciju za pripremu digitalnih Etsy oglasa. Nije još povezan sa Etsy nalogom i ne objavljuje proizvode dok se ne podese Etsy OAuth podaci i bezbedno serversko okruženje.

## Šta trenutno radi
- Unos naslova, opisa, cene, količine i tagova
- Izbor PDF-a i slika sa uređaja
- Pregled podataka i izvoz JSON nacrta oglasa
- Osnovna serverska ruta za proveru da aplikacija radi

## Šta još mora da se podesi za stvarnu Etsy automatizaciju
1. Postaviti aplikaciju na hosting koji podržava Node.js i HTTPS.
2. U Etsy Developer aplikaciji dodati tačan HTTPS Redirect URI koji daje hosting.
3. Implementirati OAuth 2.0 autorizaciju sa Etsyjem i tražene scope dozvole (npr. `listings_r` i `listings_w`).
4. API key/shared secret i OAuth tokene čuvati samo u serverskim environment promenljivama — nikad u HTML-u, porukama ili javnom repozitorijumu.
5. Testirati prvo kreiranje nacrta oglasa, zatim slanje PDF-a i slika, pa tek onda objavljivanje.

Zvanična Etsy dokumentacija:
- https://developers.etsy.com/documentation/essentials/authentication/
- https://developers.etsy.com/documentation/tutorials/listings/

## Pokretanje na računaru ili Node.js hostingu
Potreban je Node.js 18 ili noviji.

```bash
npm install
npm start
```

Zatim otvoriti `http://localhost:3000`.

Napomena: Android telefon sam po sebi nije hosting za stalno pokretanje servera. Interfejs može da se otvara u mobilnom pregledaču kada se aplikacija postavi na hosting.

## Bezbednost
Nemoj nikome slati `shared_secret`, access token ili refresh token. Ako je tajna već javno otkrivena, opozovi/rotiraj je u Etsy Developer podešavanjima.
