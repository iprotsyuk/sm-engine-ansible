- SM webapp:
  - users can't login at all, we can introduce local mode with a single always logged-in admin
  - configure storage (default is /tmp/ which might not have enough disk space)
    - hardcoded paths in fineuploaderlocalmiddleware and src/util.js need to be taken from configs

- don't rely on sudo group having NOPASSWD, supply our own /etc/sudoers
- @reboot supervisord in ubuntu user crontab

- before distributing:
* get rid of ssh keys inside the container or provide default ones
* edit crontab to start supervisor on boot
* clean up caches (apt, conda, /tmp)
