1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

	Команда:
	git log aefea
	
	Вывод:
	commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545
	Update CHANGELOG.md

2. Какому тегу соответствует коммит 85024d3?

	tag: v0.12.23

3. Сколько родителей у коммита b8d720? Напишите их хеши.

	Команда:
	git show --pretty=format:" %P" b8d720
    
	Вывод:
	56cd7859e05c36c06b56d013b55a252d0bb7e158 9ea88f22fc6269854151c571162c5bcf958bee2b
	
	Ответ: 2 родителя


4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.

	Команда:
	git log v0.12.23..v0.12.24 --oneline

	Вывод:
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

5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так 
    func providerSource(...) (вместо троеточий перечислены аргументы).
	
	Команда:
	git log -S 'func providerSource(' --oneline

	Вывод:
	8c928e835 main: Consult local directories as potential mirrors of providers
	
6. Найдите все коммиты в которых была изменена функция globalPluginDirs.

	Команда для определения имения файла:
	git grep 'func globalPluginDirs('

	Вывод:
	plugins.go:func globalPluginDirs() []string {
	
	Далее запросить коммиты, где функция была изменена:
	git log -L :globalPluginDirs:plugins.go

7. Кто автор функции synchronizedWriters?

	Команда:
	git log -S 'func synchronizedWriters' --pretty=format:'%h - %an %ae'

	Вывод:
	5ac311e2a - Martin Atkins mart@degeneration.co.uk
