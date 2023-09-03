# Windows-Defender-Firewall
|     | Description |
|-----|-------------|
| 1-  | Configurer les règles du pare-feu à l'aide de Windows Defender Firewall |
| 2-  | Configurer les règles du pare-feu à l'aide de Windows Defender Firewall avec Advanced Security |

## 1- Configurer les règles du pare-feu à l'aide de Windows Defender Firewall
1- Cliquez le boutton **Start** et selectionnez **Windows Security**

![](https://imgur.com/V1hvo8X.png)

2-Cliquez **Firewall & network protection**

![](https://imgur.com/AO7Vdwm.png)

3- Ici, vous verrez l'état du pare-feu pour ce qui suit :

    -Réseau de domaine: Les réseaux de domaine sont des workplace newtworks. Un ordinateur doit faire partie du domaine pour communiquer avec d'autres ordinateurs de ce réseau.
    -Réseau privé: Les réseaux privés sont des réseaux découvrables, ce qui signifie que seuls les appareils de ce réseau peuvent voir ou découvrir d'autres appareils sur ce même réseau. Les réseaux domestiques en sont un bon exemple.
    -Réseau public : Les réseaux publics sont des réseaux non découvrables. Un réseau non découvrable est un réseau où votre appareil ne peut pas être découvert par d'autres appareils de votre réseau. Un café ou une bibliothèque en est un bon exemple. Vous ne voulez pas que d'autres personnes puissent découvrir votre appareil.

![](https://imgur.com/2A7QUka.png)

4-Cliquez sur **Domain newtwork**

5-Vérifiez que le pare-feu Windows Defender est activé. Notez la case à cocher sous "Connexions entrantes". Il s'agit d'un emplacement d'accès rapide qui bloque tout le trafic entrant du réseau de domaine, même le trafic normalement autorisé. Sélectionnez le bouton flèche arrière pour revenir à la fenêtre "Protection du pare-feu et du réseau".

 ![](https://imgur.com/yJe0BHx.png)

 6-Répétez les étapes 4 et 5 pour le réseau privé et public.

 7- Cliquez sur **Allow an app through the firewall**

 ![](https://imgur.com/iqZq8ox.png)

 8- Faites défiler jusqu'à Mozilla Firefox. Remarquez que la configuration actuelle autorise Firefox à communiquer sur le réseau privé, mais l'empêche de communiquer sur le réseau public.

 ![](https://imgur.com/RJZgKXf.png)

 9-Cliquez sur la case "Public" à côté de Firefox. Une coche apparaîtra. Cliquez sur OK pour revenir à l'écran "Protection du pare-feu et du réseau". Les utilisateurs pourront maintenant utiliser Mozilla Firefox sur le réseau public.

 ## 2- Configurer les règles du pare-feu à l'aide de Windows Defender Firewall

Configurer les règles du pare-feu à l'aide de Windows Defender Firewall avec Advanced Security

Nous voulons utiliser le Pare-feu Windows Defender avec Sécurité avancée pour modifier une règle de pare-feu existante. Nous souhaitons appliquer les règles suivantes :

-Autoriser la connexion pour le service de gestion des clés (Key Management Service) sur le réseau de domaine et le réseau privé.

-Refuser la connexion pour le service de gestion des clés sur le réseau public.

1- Selectionnez **Advanced settings**

![](https://imgur.com/okAGhuu.png)

Ici, vous verrez un aperçu dans le panneau central. Notez particulièrement les deux types de règles répertoriés dans le panneau de gauche :

Règles entrantes (Inbound rules) : Les règles entrantes déterminent quel trafic est autorisé vers l'ordinateur.

Règles sortantes (Outbound rules) : Les règles sortantes déterminent quel trafic est autorisé à quitter l'ordinateur.

Chacune de ces règles peut être configurée pour filtrer le trafic en fonction des ordinateurs, des utilisateurs, des applications, des ports, des protocoles, etc.
2-Cliquez sur "Règles entrantes (Inbound rules)".

![](https://imgur.com/hNcXYjk.png)

3-Ici, vous verrez une longue liste de règles entrantes. Notez que certaines règles ont une coche verte à côté d'elles. Cela indique que la règle est activée pour permettre la communication entrante. Les règles sans coche sont disponibles mais ne sont pas activées.

4-Faites défiler jusqu'à la règle entrante du service de gestion des clés (Key Management Service) dans le panneau Aperçu (Overview) de Windows Defender Firewall avec Sécurité avancée. Notez ce qui suit :

La stratégie n'est actuellement pas activée (la colonne "Activée" indique "Non").
Si activée, la règle autoriserait la communication (la colonne "Action" indique "Autoriser").
Double-cliquez sur cette règle.

![](https://imgur.com/ePhGGi4.png)

5-Ici, vous verrez les détails de cette règle. Vous remarquerez que l'onglet "Général" comprend le nom de la règle, une description de la règle et indique si la règle a été autorisée ou bloquée. Dans ce cas, la connexion est autorisée. Cliquez sur l'onglet "Avancé".

![](https://imgur.com/undefined.png)

6-Ici, vous verrez à quels profils la règle s'applique. Dans ce cas, les profils Domaine, Privé et Public sont tous sélectionnés.

![](https://imgur.com/CJcpgEw.png)

7-Étant donné que nous souhaitons autoriser la communication uniquement avec les réseaux de domaine et privés, la case correspondant à "Public" ne doit pas être cochée. Ensuite, cliquez sur "Appliquer" puis sur "OK".

8-Maintenant, nous allons créer une règle entrante qui bloque la communication avec le réseau public. Comme la nouvelle règle sera similaire à la précédente, nous allons copier la règle existante. Cliquez avec le bouton droit de la souris sur la règle entrante "Key Management Service (TCP-In)" et cliquez sur "Copier". Appuyez sur Ctrl+V pour coller.

9-Vous verrez maintenant une deuxième règle entrante "Key Management Service (TCP-In)". Double-cliquez sur la deuxième règle pour ouvrir les propriétés de "Key Management Service (TCP-In)".

![](https://imgur.com/ZUIfPr0.png)

10-Puisque nous voulons bloquer la connexion avec le réseau public, sélectionnez "Bloquer la connexion" dans l'onglet "Général". Cliquez sur "Appliquer".

![](https://imgur.com/7c7xS1y.png)

11-Cliquez sur l'onglet "Avancé".

12-Cliquez sur les cases "Domaine" et "Privé" pour supprimer les coches. Cliquez sur la case "Public" pour y ajouter une coche. Cliquez sur "OK".

13-Le panneau Aperçu affichera vos modifications. Cliquez avec le bouton droit de la souris sur chaque règle "Key Management Service (TCP-In)" et cliquez sur "Activer la règle" (Enable rule).

14-Maintenant, vous verrez qu'une coche verte apparaît à côté de la première règle, ce qui indique que la règle autorisant la communication est activée. Un cercle avec une ligne à travers apparaît à côté de la deuxième règle, ce qui indique que la règle bloquant la communication est activée.

![](https://imgur.com/K6sl8ww.png)
