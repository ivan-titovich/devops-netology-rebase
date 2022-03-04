# Ветвления в git
https://github.com/ivan-titovich/devops-netology-rebase

## 2.4. Инструменты Git

1.  Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea
	Полный хэш: aefead2207ef7e2aa5dc81a34aedf0cad4c32545
	Комментарий: Update CHANGELOG.md
	git show aefea
2.  Какому тегу соответствует коммит 85024d3?
	tag: v0.12.23
3. Сколько родителей у коммита b8d720? Напишите их хеши.
	Посмотреть в псевдо-графическом виде: git log --pretty=format:'%h %s' --graph b8d720
	Посмотреть предков явно:
	git show b8d720^1
	git show b8d720^2
	Итого предки:
	a. 56cd7859e 
	b. 9ea88f22f
4.   Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.
	git log v0.12.23..v0.12.24 --oneline 

	33ff1c03b (tag: v0.12.24) v0.12.24
	b14b74c49 [Website] vmc provider links
	3f235065b Update CHANGELOG.md
	6ae64e247 registry: Fix panic when server is unreachable
	5c619ca1b website: Remove links to the getting started guide's old location
	06275647e Update CHANGELOG.md
	d5f9411f5 command: Fix bug when using terraform login on Windows
	4b6d06cc5 Update CHANGELOG.md
	dd01a3507 Update CHANGELOG.md
	225466bc3 Cleanup after v0.12.23 release

5.   Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).
	git log -S'' --oneline

	Изменена в коммите (21 апреля 2020):	5af1e6234 main: Honor explicit provider_installation CLI config when present
	Создана в коммите (2 апреля 2020):	8c928e835 main: Consult local directories as potential mirrors of providers


6.   Найдите все коммиты в которых была изменена функция globalPluginDirs.
	git log -S'globalPluginDirs' --oneline

	35a058fb3 main: configure credentials from the CLI config file
	c0b176109 prevent log output during init
	8364383c3 Push plugin discovery down into command package

7.   Кто автор функции synchronizedWriters?

	commit 5ac311e2a91e381e2f52234668b49ba670aa0fe5
	Author: Martin Atkins <mart@degeneration.co.uk>
	Date:   Wed May 3 16:25:41 2017 -0700

