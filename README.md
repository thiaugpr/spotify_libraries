# spotify_libraries
Some files required to run the local music files in Ubuntu 16.04 LTS on Spotify 1.0.28.89.
#
# Instalation:
1. Install some packs: ubuntu-restricted-extras, ffmpeg, libavcodec, livavutil, libavformat, zenity.
 
  ```
  sudo apt install ubuntu-restricted-extras ffmpeg libavcodec-extra libavcodec-extra57 libavutil55 libavformat57 zenity -y
  ```
  
2. Get required lib files.

  git clone https://github.com/thiaugpr/spotify_libraries.git

3. Put all the files in to /usr/lib/x86_64-linux-gnu/ with root privileges.

  ```
  cd spotify_libraries
  sudo cp lib* /usr/lib/x86_64-linux-gnu/
  ```

4. Execute: ldconfig
 
  ```
  sudo ldconfig
  ```
  
  If you have any link problem, make new links.
 
  e.g.: `/sbin/ldconfig.real: /usr/lib/x86_64-linux-gnu/libavutil.so.52 it's not a symbolic link`
  
  So, execute command:
  
  ```
  sudo ln -frs /usr/lib/x86_64-linux-gnu/libavutil.so.52.6.100 /usr/lib/x86_64-linux-gnu/libavutil.so.52
  sudo ln -frs /usr/lib/x86_64-linux-gnu/libavformat.so.54.36.100 /usr/lib/x86_64-linux-gnu/libavformat.so.54
  sudo ln -frs /usr/lib/x86_64-linux-gnu/libavcodec.so.54.71.100 /usr/lib/x86_64-linux-gnu/libavcodec.so.54
  ```
  And so on...
