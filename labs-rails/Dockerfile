FROM fedora23-systemd

RUN dnf install -y rubygem-rails ruby-devel mysql-devel postgresql-devel sqlite-devel systemtap-devel rpmdevtools nodejs
#                      rails         ffi       mysql         sqlite         sqlite         ffi            ffi     js env

RUN useradd -u 1000 labsapp
RUN mkdir /labsapp
RUN chown -R labsapp:labsapp /labsapp

# DB env when a db container is linked. Run "source /.db_env" to config db to app envs for app to call directly.
ADD db_env /.db_env
RUN chown labsapp:labsapp /.db_env

USER labsapp