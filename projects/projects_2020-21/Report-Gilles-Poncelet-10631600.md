# Open Source Contribution Project
*Author :* Gilles Poncelet

*Date :* September-December 2020  
*NOMA :* 1063-16-00

## Research and Selection of the Project

I have several projects in mind I would like to contribute to. However, at this moment, I still have no idea what kind of contribution I might be able to do (either for difficulty reasons or simply by a lack of ideas). Therefore, I first wanted to simply list some ideas here and will eventually choose a specific one.

#### Mariant NMT

This is an open-source Neural Machine Translation used by Microsoft. I recently used it in a fun project that was sort of a challenge from a friend. You can find more details about it [here](https://github.com/SnaKyEyeS/NeoLanguage). \
However I fear this might be a little too complex a project to be properly able to contribute as my knowledge in Deep Learning or Machine Leanrning in general is limited. \
Marian's website can be found [here](https://marian-nmt.github.io/) and its dev repo [here](https://github.com/marian-nmt/marian-dev).


#### Flask

With two friends, we've created a web-application called [ADE-Scheduler](https://ade-scheduler.info.ucl.ac.be) - which is itself an [open source project](https://github.com/SnaKyEyeS/ADE-Scheduler). This application uses the Flask micro-framework as its backend fondation. As opposed to Django, it is not "battery-included", meaning that it relies on a lot of independtly maintained packages so that one might be able to build a complete application. \
More specifically, we've been using the excellent [Flask-Security](https://github.com/Flask-Middleware/flask-security) package (among many others...) to manage all security aspects (login, user regsitration, user confirmation, etc.) of our website. While this is a great package, it is still under very active development and I would love to be able to contribute, simply to fix some bugs we've potentially encountered during our use of this package or even to participate to the development of the currently work-in-progress 4.0 release.


## First contribution: Flask-Security

In our application, when you register a new account, you need to confirm your email address before anything else. Thus, when you try to login with an unconfirmed account, it reloads the page and outputs an error message "Email requires confirmation". However, in my view, it would have been cleaner to directly redirect the user to the "resend confirmation" directly.

Being unable to do so without modifying Flask-Security's source code, I created a [new issue](https://github.com/Flask-Middleware/flask-security/issues/391) to see if the folks over there would be interested by such an option. Quickly, they answered and invited me to issue a PR on my own.

#### First review

I quickly put together a code to implement the aforementioned feature and thought "this is so simple it shouldn't require any unit test, right ?". So, I wrote my code, committed it and issued the PR - you can find it [here](https://github.com/Flask-Middleware/flask-security/pull/393).

#### Second review

Obviously, unit test are important. So I was asked to write one for my new option. Well... that was the complicated part ! Since I had never used `pytest` before, writing the following lines took me way more time than I would be willing to share:

```python
@pytest.mark.registerable()
@pytest.mark.settings(requires_confirmation_error_view="/confirm")
def test_requires_confirmation_error_redirect(app, clients):
    data = dict(email="jyl@lp.com", password="awesome sunset")
    response = clients.post("/register", data=data)

    response = authenticate(clients, **data, follow_redirects=True)
    assert b"send_confirmation_form" in response.data
    assert b"jyl@lp.com" in response.data
```

#### Third review

The maintainer of the project was happy of the work I did, but asked me to implement the same code for other endpoints as to unify the behavior accross every endpoint - which I had not thought of since I did not use these other part of the Flask-Security package in our application. Once I did that, the PR was accepted and merged. Success !

## Conclusion
You can now create an account on [ADE-Scheduler](https://ade-scheduler.info.ucl.ac.be/register), try to login before confirming your email only to be properly redirected to the `/confirm` endpoint ! \
Also: unit test are very important and not to be neglected... and thanks to this whole contribution experience, we actually integrated Travis CI & started writing tests for ADE-Scheduler as well to enable other people to contribute to the project more easily.


# Examen - L'Open Source dans les échecs

- Lichess: créé en 2010 par Thibault Duplessis
  - A nice [presentation](https://www.youtube.com/watch?v=LZgyVadkgmI) done by him
  - Initial purpose: playing around with new AJAX features
  - Second plus gros site d'échecs en ligne après chess.com
  - Business plan = pas de business plan ! C'est un vrai "free software" (100% gratuit, 100% ad-free) sous la license AGPLv3
  - Donations pour financer leurs ~10 serveurs principaux et c'est tout
  - Grande liberté par rapport à la concurrence qui sont tous "propriétaires" (chess.com, chess24.com, etc.)
  - Prouve que il est tout à fait possible d'avoir des vrais free software qui ne sont pas "money-driven" et de concurrencer les boites "capitalistes" (par opposition aux jeux "gratuits" mais pay2win)

- Engine analysis
  - Feature: analyser les partie avec un engine d'échecs
  - Très CPU gourmand, besoin de grosse puissance de calcul
  - Solution: [FishNet](https://github.com/niklasf/fishnet) (codé par un contributeur pour Lichess), une solution décentralisée
  - Résultat: décentralisation de l'analyse de parties sur 300+ serveurs prêtés par des internautes du monde entier

- [Stockfish](https://github.com/official-stockfish/Stockfish) & [LeelaChessZero](https://github.com/LeelaChessZero/lc0)
  - Meilleure entités d'échec au niveau mondial (license GPLv3), utilisé par tous les GM
  - Lc0 est basée sur l'engine propriétaire de Google Deepmind, AlphaZero (reconstruite par la communauté sur base de l'architecture de AlphaZero)
  - Parler de la [TCEC](https://tcec-chess.com/) (où Lc0 affronte actuellement Stockfish)

- Conclusion
  - Le monde des échecs prouve qu'il est possible de produire le state-of-the art dans un domaine en juste en utilisant la force de la communauté open source.
  - Comme le dit Thibault Duplessis: c'est parfois même avantageux ! Certains outils comme Slack, Travis, etc sont gratuits pour les projets open source et coutent bonbon pour des entreprises...
  - Pas de contraintes "gérer ses employés", etc. Juste une bande de joyeux lurons qui veulent faire partie d'un projet qui est plus grand qu'eux.
