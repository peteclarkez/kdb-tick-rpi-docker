FROM peteclarkez/kdb-tick-docker as kdbtick

####

FROM peteclarkez/embedpypi as embedpypi

ENV Q_TICKHOME=/opt/kx/kdb-tick

COPY --from=kdbtick $Q_TICKHOME $Q_TICKHOME

RUN chmod 774 $Q_TICKHOME && \
    chmod 774 $Q_TICKHOME/tick && \
    chmod a+x /opt/kx/kdb-tick/tick.sh && \ 
    chown -R kx:kx $Q_TICKHOME

ENTRYPOINT ["/init"]
CMD ["/opt/kx/kdb-tick/tick.sh"]