# deactivate multiple nextcloud apps
deactivate mulitple nextcloud apps at once
With the latest upgrade to 24.0.4 I got an error something went not good while upgrading, out of my experience it's belonging to apps they are not supporting the newer versions of Nextcloud. I was looking for a way to deactivate them all in one command.

0. `sudo -u www-data php /var/www/nextcloud/occ maintenance:mode --off`
1.  I did a list `sudo -u www-data php /var/www/nextcloud/occ app:list >> ~/app.list` 
2. I edit the list and took out all the version numbers and listing singes
3. I wehre running the list througt a variable with `for i in $(cat ~/app.list) do  sudo -u www-data php /var/www/nextcloud/occ app:disable $i; done`
4. and than `sudo -u www-data php /var/www/nextcloud/occ upgrade` agian
