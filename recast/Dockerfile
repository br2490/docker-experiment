# syntax=docker/dockerfile:experimental
FROM islandora/crayfish:latest

RUN --mount=id=composer,sharing=locked,type=cache,target=/root/.composer/cache \
    composer install -d /var/www/crayfish/Recast && \
    ln -s /var/www/crayfish/Recast/src /var/www/html && \
    cleanup.sh

COPY /rootfs /

RUN chown -R nginx:nginx /var/www

WORKDIR /var/www/crayfish/Recast/
