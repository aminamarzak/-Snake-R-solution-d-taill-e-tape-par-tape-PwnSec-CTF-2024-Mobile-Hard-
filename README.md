# -Snake-R-solution-d-taill-e-tape-par-tape-PwnSec-CTF-2024-Mobile-Hard-

Objectif du challenge
L’application Android implémente plusieurs mécanismes de protection anti-reverse (détection de root, détection d’émulateur et détection de Frida via la librairie native). Elle lit un fichier YAML depuis le stockage externe et le parse en utilisant une version vulnérable de SnakeYAML (probablement la version 1.33, vulnérable à CVE-2022-1471).
L’objectif est d’exploiter cette vulnérabilité de désérialisation unsafe pour instancier une classe cachée nommée BigBoss. Cette classe charge une librairie native et, lorsqu’elle reçoit la bonne chaîne en paramètre, appelle une fonction JNI qui génère et affiche le flag dans les logs Android (logcat).
Contrairement à FireStorm, Frida ne peut pas être utilisé ici à cause des détections natives. La solution repose sur du patching statique de l’APK et une payload de désérialisation YAML.
Niveau : Hard
Techniques principales : Analyse statique approfondie (Jadx + apktool), patching Smali pour bypasser les anti-debug/anti-root, exploitation de désérialisation SnakeYAML (CVE-2022-1471), utilisation d’Intent via ADB, et récupération du flag via logcat.

<img width="787" height="317" alt="image" src="https://github.com/user-attachments/assets/1f32d60f-731c-44fd-9ded-e8a1352c3638" />

<img width="768" height="150" alt="image" src="https://github.com/user-attachments/assets/75773034-e370-4663-97a7-dc5c64115dac" />

<img width="822" height="412" alt="image" src="https://github.com/user-attachments/assets/d54a124f-3326-4bc5-83aa-a3ca4b961901" />

<img width="617" height="167" alt="image" src="https://github.com/user-attachments/assets/e4fa2e45-814b-45b3-bf3c-4c93f27570d0" />

<img width="1047" height="413" alt="image" src="https://github.com/user-attachments/assets/a2343145-b792-45a6-90e2-25da699124c1" />

<img width="887" height="170" alt="image" src="https://github.com/user-attachments/assets/70f2b257-d229-4aa7-a016-adb30ba3d008" />

<img width="976" height="136" alt="image" src="https://github.com/user-attachments/assets/88eddf55-4650-4c64-896a-77f8a4816b74" />

<img width="373" height="787" alt="image" src="https://github.com/user-attachments/assets/db305271-1c7d-4a21-9b15-2e13c717a647" />






