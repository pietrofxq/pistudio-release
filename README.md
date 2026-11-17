# pistudio

pistudio is a Windows app for recording a music cover one part at a time, syncing the takes, composing a multicam
video and exporting it for Reels, Shorts, TikTok and YouTube. It runs on your PC: there is no account and nothing
is hosted.

This repository holds the installers and nothing else. The source is kept elsewhere.

## Install

1. Open [the latest release](../../releases/latest) and download `pistudio-Setup-X.Y.Z.exe`.
2. Run it. Windows says **Windows protected your PC**, because the installer is not signed with a publisher's
   certificate yet: choose **More info**, then **Run anyway**. If **Smart App Control** is on, Windows blocks
   unsigned apps and offers no way past it.
3. Keep the folder it offers or choose another. It installs for your Windows user only and asks for no
   administrator rights.

pistudio needs 64-bit Windows 10 or 11, and ffmpeg with ffprobe, version 8 or later, which it does not bring with it.
One way to get them is `winget install Gyan.FFmpeg` in a terminal; pistudio finds them by itself, or you point it to
them in **Settings**, under **Media toolchain**.

## Check your download

Each release lists the SHA-256 checksum of its files in `SHA256SUMS.txt`. In PowerShell:

```
Get-FileHash .\pistudio-Setup-X.Y.Z.exe -Algorithm SHA256
```

The line it prints must match the installer's line in that file.

## Update

pistudio updates itself. Now and then it looks in this repository for a newer version, downloads it in the
background and installs it when you close the app; **Restart to update**, in **Settings** under **App**, installs
it at once and opens pistudio again. Nothing starts while you record, and nothing is sent but the request for the
update. Turn **Update automatically** off there and pistudio asks for nothing by itself: **Check for updates** then
looks when you click it, and **Download** fetches what it found. **What’s new** lists the changes in the version
you are running.

An update is not signed by a publisher either. The app checks each download against the checksum this repository
publishes with it.

To update by hand, download the newer installer and run it: it installs over the older one. Close pistudio first;
the installer waits for it and never closes it for you, so a take or a render is not cut short.

Your songs (in `Documents\Covers\library`, unless you chose another folder) and the app's own data are left alone.
Do not keep songs inside the folder pistudio is installed in: every update replaces that folder, and the app refuses
to use it as its library.

Only install a newer version over an older one. An older pistudio does not open data a newer one has used, and says
so when it starts.

## Uninstall

In Windows, **Settings**, **Apps**, **Installed apps**. Your songs and the app's data stay where they are.

## Em português

O pistudio é um app para Windows que grava um cover uma parte de cada vez, sincroniza as gravações e monta um vídeo
com várias câmeras. Baixe `pistudio-Setup-X.Y.Z.exe` na [versão mais recente](../../releases/latest) e execute. O
Windows avisa que protegeu o computador, porque o instalador ainda não é assinado: escolha **Mais informações** e
depois **Executar assim mesmo**. O pistudio precisa do ffmpeg 8 ou mais novo instalado. O pistudio se atualiza
sozinho: procura uma atualização de tempos em tempos, baixa em segundo plano e instala quando você fecha o app; em
**Configurações**, em **App**, **Atualizar automaticamente** desliga isso. Para atualizar à mão, feche o pistudio e
execute o instalador mais novo por cima. Suas músicas e os dados do app ficam como estão.

## En español

pistudio es una aplicación para Windows que graba un cover parte por parte, sincroniza las tomas y compone un vídeo
con varias cámaras. Descarga `pistudio-Setup-X.Y.Z.exe` de la [versión más reciente](../../releases/latest) y
ejecútalo. Windows avisa de que protegió el equipo, porque el instalador todavía no está firmado: elige **Más
información** y después **Ejecutar de todas formas**. pistudio necesita ffmpeg 8 o posterior instalado. pistudio
se actualiza solo: busca una actualización cada cierto tiempo, la descarga en segundo plano y la instala al cerrar
la aplicación; en **Configuración**, en **Aplicación**, **Actualizar automáticamente** lo desactiva. Para
actualizar a mano, cierra pistudio y ejecuta el instalador más nuevo encima. Tus canciones y los datos de la
aplicación se quedan como están.
