# Рабочее окружение на базе Vagrant.

1. Во всех проектах, которые предполагают серверную часть, для разворачивания окружения разработчика должен использоваться Vagrant.
2. В началале проекта PM должен назначить ответственного за создание и ПОДДЕРЖАНИЕ в актуальном состоянии настроек vagrant.
3. Настройки vagrant должны храниться в репозитроии проекта, с соблюдением следующих правил.
  - Доступ на изменение настроек должен быть предоставлен только ответственному за это лицу.
  - Окружения всех разработчиков должны быть развернуты с использованием подготовленного конфигурационного файла.
  - Разворачивание проекта любым разработчкиом должно осуществляться путем выполнения двух команд git clone и vagrant up.
4. При конфигурировании Vagrant РЕКОМЕНДУЕТСЯ:
  -	всегда использовать последнюю версию Vagrant;
  -	всегда использовать последнюю версию Virtual Box, в качестве драйвера виртуализации;
  -	в качестве провиизи использовать ansible либо chef_solo;
  -	в качестве режима синхронизации должен быть использован nfs либо rsync для linux и default для windows;
  -	(опционально) директория проекта должна подключатся к папке /vagrant на гостевой машине (таким образом на любой вагрантовской виртуальной машине мы будем знать куда идти, чтобы попасть в директорию проекта)
  -	проверить конфигурацию  на Linux/Windows.
5. Рекомендуемые Vagrant plugins  
  -	[vagrant-hostmanager](https://github.com/smdahlen/vagrant-hostmanager) плагин для синхронизации /etc/hosts файла на хостовой машине;
  - [vagrant-bindfs](https://github.com/gael-ian/vagrant-bindfs) a Vagrant plugin to automate bindfs mount in the VM. This allow you to change owner, group and permissions on files and, for example, work around NFS share permissions issues.
  - [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest) is a Vagrant plugin which automatically installs the host's VirtualBox Guest Additions on the guest system.
  - [vagrant-omnibus](https://github.com/chef/vagrant-omnibus) is a vagrant plugin that ensures the desired version of Chef is installed via the platform-specific Omnibus packages.
6.	При конфигурировании vagrant ЗАПРЕЩЕНО:
  -	реализовать только часть настройки, к примеру только связанную с бекендом. 
  -	использовать ОС-специфические настройки Vagrant
  -	править настройки Vagrant без согласования с командой.

# Готовые сборки Vagrant

 - [WordPress Application Box](https://github.com/CodeTiburon/wp-box)

