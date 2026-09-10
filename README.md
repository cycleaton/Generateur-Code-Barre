GENERATEUR DE CODES-BARRES
===========================

CONTENU DU DOSSIER
-------------------
- GenerateurCodeBarre.exe  -> l'application, prete a l'emploi (le logo est integre dedans).
- Program.cs                -> le code source (C#).
- build.ps1                  -> script pour recompiler l'exe si vous modifiez Program.cs.
- logo.png                   -> image d'origine du logo.
- logo_app.png                -> logo recadre en carre, integre dans l'exe (en-tete + fenetre Credits).
- logo.ico                    -> icone multi-resolution generee a partir du logo, integree dans l'exe
                                  (icone du fichier .exe, de la fenetre et de la barre des taches).

Seul GenerateurCodeBarre.exe est necessaire pour utiliser l'application : le logo et
l'icone sont deja integres dedans (fichier autonome, rien d'autre a copier).

UTILISATION
-----------
Double-cliquez simplement sur GenerateurCodeBarre.exe.

1. Choisissez le type de code-barres :
   - Code 39      : texte libre (lettres A-Z, chiffres, espace et - . $ / + %)
   - EAN-13        : 12 chiffres, la 13e cle de controle est calculee automatiquement
   - UPC-A         : 11 chiffres, la 12e cle de controle est calculee automatiquement
2. Saisissez la valeur, cliquez sur "Generer".
3. Ajustez si besoin la largeur des barres / la hauteur.
4. Enregistrez en PNG, copiez l'image dans le presse-papiers, ou imprimez directement.

FONCTIONNE HORS RESEAU ET SUR N'IMPORTE QUEL PC WINDOWS
---------------------------------------------------------
L'application est un simple .exe autonome (WinForms / .NET Framework).
Elle ne se connecte a AUCUN reseau et ne necessite AUCUNE installation :
copiez juste GenerateurCodeBarre.exe (une seule fois si vous voulez, ou avec
tout le dossier) sur une cle USB ou un autre PC Windows, meme sans acces internet,
et lancez-le directement.

Seule condition : le PC cible doit avoir le .NET Framework 4.x, ce qui est le cas
par defaut sur pratiquement tous les Windows depuis Windows 7 SP1 / Windows Server 2008 R2
(inclus nativement dans Windows 10 et Windows 11). Aucune installation supplementaire
n'est necessaire dans l'immense majorite des cas.

MODIFIER / RECOMPILER
----------------------
Si vous modifiez Program.cs, relancez simplement :
    powershell -ExecutionPolicy Bypass -File build.ps1
Cela recree GenerateurCodeBarre.exe (le compilateur C# est deja integre a Windows,
aucun logiciel a installer).

LIMITES ACTUELLES
------------------
- Formats geres : Code 39, EAN-13, UPC-A (les plus courants pour l'etiquetage et le
  commerce). Le format Code 128 ou les QR codes ne sont pas inclus dans cette version,
  mais peuvent etre ajoutes sur demande.
