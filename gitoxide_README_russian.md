[![CI](https://github.com/GitoxideLabs/gitoxide/workflows/ci/badge.svg)](https://github.com/GitoxideLabs/gitoxide/actions)
[![Crates.io](https://img.shields.io/crates/v/gitoxide.svg)](https://crates.io/crates/gitoxide)
<img src="etc/msrv-badge.svg">

`gitoxide`:это реализация "git", написанная на Rust для разработки перспективных приложений, которые стремятся к корректности и
производительности, обеспечивая при этом приятный и не вызывающий удивления опыт разработчика.

Существует два основных способа использования `gitoxide`

1. **As Rust library**: Use the [`gix`](https://docs.rs/gix) crate как зависимость от Cargo для доступа к API.
1. **As command-line tool**: The `gix` бинарный файл как инструмент разработки, помогающий тестировать API в реальных репозиториях,
    and the `ein` двоичный файл с инструментами, улучшающими рабочий процесс. Оба двоичных файла могут постоянно оставаться нестабильными,
    *не используйте их в сценариях*.

[![asciicast](etc/gix-asciicast.svg)](https://asciinema.org/a/542159)

[`gix`]: https://docs.rs/gix

## Статус разработки

Инструменты командной строки, а также статус каждого контейнера описаны в
[the crate status document](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md).

Для использования в приложениях найдите [`gix`](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix) ящик,
который служит отправной точкой для доступа к функциональным возможностям, предоставляемым различными сантехническими ящиками более низкого уровня, такими как
[`gix-config`](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-config).

###  Обнаружение функций

> Может ли "gix" выполнять то, что мне нужно?

На этот вопрос может быть сложно ответить, и этот абзац здесь для того, чтобы помочь с обнаружением функций.

Смотреть на[`crate-status.md`](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md) для получения довольно исчерпывающего документа, содержащего
как реализованные, так и запланированные функции.

Further, the [`gix` crate documentation with the `git2` search term](https://docs.rs/gix/latest/gix?search=git2) помогает найти все
известные на данный момент эквивалентные вызовы методов git2. Пожалуйста, обратите внимание, что этот список, безусловно, еще не является исчерпывающим, но может помочь, если вы используете git2.

Ниже приведен высокоуровневый список функций и тех, которые планируются:

* [x] clone
* [x] fetch
* [ ] push
* [x] blame (*plumbing*)
* [x] status
* [x] blob and tree-diff
* [ ] merge
    - [x] blobs
    - [x] trees
    - [ ] commits
* [x] commit
    - [ ] hooks
* [x] commit-graph traversal
* [ ] rebase
* [x] worktree checkout and worktree stream
* [ ] reset
* [x] reading and writing of objects
* [x] reading and writing of refs
* [x] reading and writing of `.git/index`
* [x] reading and writing of git configuration
* [x] pathspecs
* [x] revspecs
* [x] `.gitignore` and `.gitattributes`

### Ящики

Для получения подробной информации о статусе, перейдите по ссылке на название ящика. Пожалуйста, обратите внимание, что все ящики указаны ниже. [semver] as well as the [stability guide] stability guide = руководство по стабильности.

[semver]: https://semver.org

### Производственный класс

* **Уровень стабильности 1**
  - [gix-lock](https://github.com/GitoxideLabs/gitoxide/blob/main/gix-lock/README.md)

* **Stability Tier 2**
  - [gix-tempfile](https://github.com/GitoxideLabs/gitoxide/blob/main/gix-tempfile/README.md)

### Кандидаты на стабилизацию

Пакеты, которые кажутся функционально завершенными и нуждаются в дополнительном использовании, прежде чем их можно будет выпустить в версии 1.0.
Документация завершена и была просмотрена как минимум один раз.

* [gix-mailmap](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-mailmap)
* [gix-chunk](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-chunk)
* [gix-ref](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-ref)
* [gix-config](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-config)
* [gix-config-value](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-config-value)
* [gix-glob](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-glob)
* [gix-actor](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-actor)
* [gix-hash](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-hash)

### Первоначальная разработка

В этих ящиках могут отсутствовать некоторые функции и, следовательно, они несколько неполны, но то, что там
есть, в некоторой степени пригодно для использования.

* **usable** _(с грубыми, но полными документами, возможно, с неполной функциональностью)_
  * [gix](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix) (**⬅ entrypoint**)
  * [gix-object](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-object)
  * [gix-validate](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-validate)
  * [gix-url](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-url)
  * [gix-packetline](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-packetline)
  * [gix-packetline-blocking](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-packetline)
  * [gix-transport](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-transport)
  * [gix-protocol](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-protocol)
  * [gix-pack](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-pack)
  * [gix-odb](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-odb)
  * [gix-commitgraph](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-commitgraph)
  * [gix-diff](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-diff)
  * [gix-traverse](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-traverse)
  * [gix-features](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-features)
  * [gix-credentials](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-credentials)
  * [gix-sec](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-sec)
  * [gix-quote](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-quote)
  * [gix-discover](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-discover)
  * [gix-path](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-path)
  * [gix-attributes](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-attributes)
  * [gix-ignore](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-ignore)
  * [gix-pathspec](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-pathspec)
  * [gix-index](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-index)
  * [gix-revision](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-revision)
  * [gix-revwalk](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-revwalk)
  * [gix-command](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-command)
  * [gix-prompt](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-prompt)
  * [gix-refspec](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-refspec)
  * [gix-fs](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-fs)
  * [gix-utils](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-utils)
  * [gix-hashtable](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-hashtable)
  * [gix-worktree](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-worktree)
  * [gix-bitmap](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-bitmap)
  * [gix-negotiate](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-negotiate)
  * [gix-filter](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-filter)
  * [gix-worktree-stream](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-worktree-stream)
  * [gix-archive](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-archive)
  * [gix-submodule](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-submodule)
  * [gix-status](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-status)
  * [gix-worktree-state](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-worktree-state)
  * [gix-date](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-date)
  * [gix-dir](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-dir)
  * [gix-merge](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-merge)
  * [gix-shallow](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-shallow)
  * `gitoxide-core`
* **very early**  _(possibly without any documentation and many rough edges)_
  * [gix-blame](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-blame)
* **idea** _(just a name placeholder)_
  * [gix-note](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-note)
  * [gix-fetchhead](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-fetchhead)
  * [gix-lfs](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-lfs)
  * [gix-rebase](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-rebase)
  * [gix-sequencer](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-sequencer)
  * [gix-tui](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-tui)
  * [gix-tix](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-tix)
  * [gix-bundle](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-bundle)
  * [gix-fsck](https://github.com/GitoxideLabs/gitoxide/blob/main/crate-status.md#gix-fsck)

### Стресс-тестирование
  * [x] Проверяйте огромные пакеты
  * [x] Разверните  пакет на диск
  * [x] Генерировать и проверять большие commit graphs
  * [ ] Generate огромные пакеты from a lot of loose objects

### Стабильность and MSRV

Our [stability guide] помогает оценить, насколько большую нагрузку можно ожидать в зависимости от количества ящиков в этом рабочем пространстве.

[stability guide]: https://github.com/GitoxideLabs/gitoxide/blob/main/STABILITY.md

## Установка

###Загрузите двоичный релиз

С помощью `cargo binstall`, один из них  [binary releases][releases]. Вы можете установить его с помощью `cargo install cargo-binstall`, предполагая,
the [rust toolchain][rustup] присутствует.

Затем установите gitoxide с помощью `cargo binstall gitoxide`.

See the [releases section][releases] для ручной установки и различных альтернативных сборок, 
которые are _slimmer_ or _smaller_, в зависимости
от ваших потребностей, for _Linux_, _MacOS_ and _Windows_.

[releases]: https://github.com/GitoxideLabs/gitoxide/releases

### Загрузить из репозитория Arch Linux

Для Arch Linux вы можете загрузить `gitoxide` из репозитория сообщества:

```sh
pacman -S gitoxide
```

### Скачать с Exherbo Linux Rust repository

For Exherbo Linux вы можете скачать `gitoxide` from the 
[Rust](https://gitlab.exherbo.org/exherbo/rust/-/tree/master/packages/dev-scm/gitoxide) repository:

```sh
cave resolve -x repository/rust
cave resolve -x gitoxide
```

### From Source via Cargo

`cargo` это менеджер пакетов Rust, который можно легко получить с помощью [rustup]. 
С его помощью вы можете легко создать свой собственный двоичный
файл для вашего конкретного процессора, что дополнительно повысит производительность.

Минимальная поддерживаемая версия Rust - это [documented in the Cargo package](https://github.com/GitoxideLabs/gitoxide/blob/main/gix/Cargo.toml#L12-L14),
the latest stable one will work as well.

Существуют различные конфигурации сборки, все они являются [documented here](https://docs.rs/crate/gitoxide/latest). 
Документация также должна быть полезна
разработчикам пакетов, которым необходимо настроить внешние зависимости.

```sh
# Способ установки `gitoxide` с установленным только Rust и компилятором C.
#  Если во время клонирования возникнут проблемы с SSL-сертификатами, попробуйте опустить`--locked`.
cargo install gitoxide --locked --no-default-features --features max-pure

# Установка по умолчанию, "max", является самой быстрой, но также требует`cmake` to build successfully.
# Installing it is platform-dependent.
cargo install gitoxide

# Для создания двоичных файлов меньшего размера и еще более быстрой сборки, которые заменяются менее сложной реализацией CLI,
# используйте функцию "lean".
cargo install gitoxide --locked --no-default-features --features lean
```

Ниже приводится установка последней неопубликованной версии `max` непосредственно из git:

```sh
cargo install --git https://github.com/GitoxideLabs/gitoxide gitoxide
```

#### Как бороться со сбоями при сборке

На некоторых платформах установка может завершиться неудачно из-за отсутствия инструментов, 
необходимых для *C* toolchains. Обычно этого можно избежать, установив с помощью:

```sh
cargo install gitoxide --no-default-features --features max-pure
```

Ниже приведен список известных сбоев.

- On Fedora, `perl` должен быть установлен для `OpenSSL` to build properly. This can be done with the following command (see [issue #592](https://github.com/GitoxideLabs/gitoxide/issues/592)):

  ```sh
  dnf install perl
  ```

### Использование Docker

Некоторые конвейеры CI/CD используют клонирование репозитория. Ниже приведен пример создания образов docker с возможностью копирования и вставки для таких рабочих процессов.
Поскольку официального образа не существует (на данный момент), сначала необходимо создать образ.

> [!NOTE]
>Файл dockerfile не тестируется постоянно, поскольку он требует слишком много времени и, следовательно, уже может быть поврежден.
> Приветствуются комментарии. 

####  Создание наиболее совместимого base image

```sh
docker build -f etc/docker/Dockerfile.alpine -t gitoxide:latest --compress . --target=pipeline
```

#### Основное использование в Pipeline
Например, если "Dockerfile" в данный момент использует что-то вроде
`RUN git clone https://github.com/GitoxideLabs/gitoxide`, first build the image:

```sh
docker build -f etc/docker/Dockerfile.alpine -t gitoxide:latest --compress .
```

Затем скопируйте двоичные файлы в свой образ и замените директиву `git` на эквивалент `gix`.

```dockerfile
COPY --from gitoxide:latest /bin/gix /usr/local/bin/
COPY --from gitoxide:latest /bin/ein /usr/local/bin/

RUN /usr/local/bin/gix clone --depth 1 https://github.com/GitoxideLabs/gitoxide gitoxide
```


[releases]: https://github.com/GitoxideLabs/gitoxide/releases
[rustup]: https://rustup.rs

## Использование

После установки остаются два двоичных файла:

* **ein**
  команды высокого уровня, _porcelain_, для повседневного использования, оптимизированные для приятного взаимодействия с пользователем* 
* **gix**
  * команды низкого уровня, _plumbing_, для использования в более специализированных случаях и для проверки недавно написанного кода в реальных сценариях.

## Цели проекта

Project goals can change over time as we learn more, and they can be challenged.

 * **реализация git в чистом виде на основе rust***
включая    *transport*, *object database*, *references*, *cli* and *tui*  * для наиболее распространенных операций git предусмотрен простой интерфейс командной строки, оптимизированный для
     пользовательский опыт. A *simple-git*, если вы так хотите.
   * станет доступной реализацией для всех, кто хочет решать проблемы, связанные с git, и в процессе станет
     * альтернативой `GitPython` и *libgit2*.
   * стать основой для распределенной альтернативы GitHub и, возможно, даже для использования в самом GitHub
 * **учитесь у лучших, чтобы создавать наилучшие идиоматические выражения Rust**
   * * libgit2 - это фантастический ресурс, позволяющий увидеть, как работают абстракции, мы будем их использовать
   * используйте систему типов Rust, чтобы исключить неправильное использование
 * **быть наиболее эффективной реализацией**
   * используйте систему типов Rust для оптимизации работы, которая не выполняется без сложностей в использовании
   * используйте параллелизм с самого начала
   * поддержка проверки разборности с первого дня
 * **assure on-disk consistency**
   * убедитесь, что операции чтения никогда не мешают одновременной записи
   * убедитесь, что несколько одновременных операций записи не вызывают проблем
 * **take shortcuts, but not in quality**
   * двоичные файлы могут использовать "anyway::Error" в полном объеме, зная, что эти ошибки возникают исключительно у пользователя.
   * библиотеки используют простые пользовательские ошибки, реализованные с помощью "quick-error" или "thiserror".
   * интернационализация - это не то, о чем мы сейчас думаем.
   * Ошибки ввода-вывода из-за недостаточного количества дескрипторов открытых файлов не всегда приводят к сбою операции
 * **Кроссплатформенная поддержка, включая Windows**
   * Благодаря инструментам и опыту, доступным здесь, нет причин отказываться от поддержки Windows.
   * [Windows is tested on CI](https://github.com/GitoxideLabs/gitoxide/blob/df66d74aa2a8cb62d8a03383135f08c8e8c579a8/.github/workflows/rust.yml#L34)
     and failures do prevent releases.


## Нецелевые задачи

Нецелевые задачи проекта могут меняться со временем по мере того, как мы узнаем больше, и их можно оспорить.

 * ** идеально воспроизводить функциональность команд git**
   * "git" - это "git", и нет причин не использовать его. Наш путь - это путь простоты в выборе
     начать работу с git несложно.
 * ** быть несовместимым с git**
   * формат на диске должен оставаться совместимым, и мы никогда не будем с этим мириться.
 * ** используйте асинхронный ввод-вывод везде**
   * по большей части операции git в значительной степени зависят от ввода-вывода с отображением в память, а также от центрального процессора для распаковки данных,
     что не очень хорошо подходит для асинхронного ввода-вывода из коробки.
   * Используйте "блокировку", а также "gix-features::interrupt", чтобы перенести операции в асинхронный мир и контролировать
     длительно выполняемые операции.
   * При подключении или потоковой передаче по TCP-соединениям, особенно при получении на сервере, асинхронность кажется обязательной
     хотя и за флагом функции.

## Содействие = Contributions = 
Если то, что вы увидели до сих пор, вызвало у вас интерес внести свой вклад, то позвольте нам сказать: мы рады видеть вас у себя и помочь вам начать.

Мы рекомендуем запустить
 `just test` в процессе разработки, чтобы убедиться, что CI является зеленым, прежде чем запускать его.

Список незавершенных работ, готовых к выполнению, находится в [available in the Project's Kanban board][project-board], который содержит инструкции о том, как
выбрать задание. Если поле пустое или у вас есть другие вопросы, не стесняйтесь обращаться [start a discussion][discussions] or reach out to @Byron [privately][keybase].

Для получения дополнительной информации также ознакомьтесь с [collaboration guide].

[collaboration guide]: https://github.com/GitoxideLabs/gitoxide/blob/main/COLLABORATING.md
[project-board]: https://github.com/GitoxideLabs/gitoxide/projects
[discussions]: https://github.com/GitoxideLabs/gitoxide/discussions
[keybase]: https://keybase.io/byronbates
[cargo-diet]: https://crates.io/crates/cargo-diet

### Getting started with Video Tutorials

- [Learning Rust with Gitoxide](https://youtube.com/playlist?list=PLMHbQxe1e9Mk5kOHrm9v20-umkE2ck_gE)
   - In 17 episodes you can learn all you need to meaningfully contribute to `gitoxide`.
- [Getting into Gitoxide](https://youtube.com/playlist?list=PLMHbQxe1e9MkEmuj9csczEK1O06l0Npy5)
   - Get an introduction to `gitoxide` itself which should be a good foundation for any contribution, but isn't a requirement for contributions either.
- [Gifting Gitoxide](https://www.youtube.com/playlist?list=PLMHbQxe1e9MlhyyZQXPi_dc-bKudE-WUw)
   - See how PRs are reviewed along with a lot of inner monologue.

#### Other Media

- [Rustacean Station Podcast](https://rustacean-station.org/episode/055-sebastian-thiel/)

## Roadmap

### Features for 1.0

Предоставлять a CLI для самого простого путешествия пользователя:

* [x] инициализируйте репозиторий
* [x] fetch
    * [ ] and update worktree
* clone a repository
   - [ ] bare
   - [ ] with working tree
* [ ] создайте "commit" после добавления файлов рабочего дерева
* [x] add a remote
* [ ] push
  * [x] create (thin) pack

### Ideas for Examples

* [ ] `gix tool open-remote` откройте URL-адрес удаленного устройства, возможно, после применения известных преобразований для перехода с "ssh" на "https".
* [ ] `tix` as example implementation of `tig`, отображение версии графика фиксации, полезной для практики создания высокочувствительных графических интерфейсов.
* [ ] Something like [`git-sizer`](https://github.com/github/git-sizer), но с использованием экстремальных скоростей распаковки индексированных пакетов.
* [ ] Open up SQL for git using [sqlite virtual tables](https://github.com/rusqlite/rusqlite/blob/master/tests/vtab.rs). Check out gitqlite
  as well. What would an MVP look like? Maybe even something that could ship with gitoxide. See [this go implementation as example](https://github.com/filhodanuvem/gitql).
* [ ] A truly awesome history rewriter which makes it easy to understand what happened while avoiding all pitfalls. Think BFG, but more awesome, if that's possible.
* [ ] `gix-tui` should learn a lot from [fossil-scm] regarding the presentation of data. Maybe [this](https://github.com/Lutetium-Vanadium/requestty/) can be used for prompts. Probably [magit] has a lot to offer, too.

### Ideas for Spin-Offs

* [ ] A system to integrate tightly with `gix-lfs` to allow a multi-tier architecture so that assets can be stored in git and are accessible quickly from an intranet location
  (for example by accessing the storage read-only over the network) while changes are pushed immediately by the server to other edge locations, like _the cloud_ or backups. Sparse checkouts along with explorer/finder integrations
  make it convenient to only work on a small subset of files locally. Clones can contain all configuration somebody would need to work efficiently from their location,
  and authentication for the git history as well as LFS resources make the system secure. One could imagine encryption support for untrusted locations in _the cloud_
  even though more research would have to be done to make it truly secure.
* [ ] A [syncthing] like client/server application. This is to demonstrate how lower-level crates can be combined into custom applications that use
  only part of git's technology to achieve their very own thing. Watch out for big file support, multi-device cross-syncing, the possibility for
  untrusted destinations using full-encryption, case-insensitive and sensitive filesystems, and extended file attributes as well as ignore files.
* An event-based database that uses commit messages to store deltas, while occasionally aggregating the actual state in a tree. Of course it's distributed by nature, allowing
  people to work offline.
    - It's abstracted to completely hide the actual data model behind it, allowing for all kinds of things to be implemented on top.
    - Commits probably need a nanosecond component for the timestamp, which can be added via custom header field.
    - having recording all changes allows for perfect merging, both on the client or on the server, while keeping a natural audit log which makes it useful for mission critical
      databases in business.
    * **Applications**
      - Can markdown be used as database so issue-trackers along with meta-data could just be markdown files which are mostly human-editable? Could user interfaces
        be meta-data aware and just hide the meta-data chunks which are now editable in the GUI itself? Doing this would make conflicts easier to resolve than an `sqlite`
        database.
      - A time tracker - simple data, very likely naturally conflict free, and interesting to see it in terms of teams or companies using it with maybe GitHub as Backing for authentication.
        - How about supporting multiple different trackers, as in different remotes?

[syncthing]: https://github.com/syncthing/syncthing
[fossil-scm]: https://www.fossil-scm.org
[magit]: https://magit.vc

## Недостатки и ограничения

Please take a look at the [`SHORTCOMINGS.md` file](https://github.com/GitoxideLabs/gitoxide/blob/main/SHORTCOMINGS.md) for details.

## Credits

* **itertools** _(MIT Licensed)_
  * We use the `izip!` macro in code
* **flate2** _(MIT Licensed)_
  * We use the high-level `flate2` library to implement decompression and compression, which builds on the high-performance `zlib-rs` crate.

## 🙏 Особая благодарность 🙏

 По крайней мере, на данный момент этот раздел является эксклюзивным, чтобы подчеркнуть невероятную поддержку, которую
 [Josh Triplett](https://github.com/joshtriplett) has provided to me
 
in the form of advice, sponsorship and countless other benefits that were incredibly meaningful. Going full time with `gitoxide` would hardly have been
feasible without his involvement, and I couldn't be more grateful 😌.

## License

This project is licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

## Fun facts

* Originally @Byron was really fascinated by [this problem](https://github.com/gitpython-developers/GitPython/issues/765#issuecomment-396072153)
  and believes that with `gitoxide` it will be possible to provide the fastest solution for it.
* @Byron has been absolutely blown away by `git` from the first time he experienced git more than 13 years ago, and
  tried to implement it in [various shapes](https://github.com/gitpython-developers/GitPython/pull/1028) and [forms](https://github.com/byron/gogit)
  multiple [times](https://github.com/Byron/gitplusplus). Now with Rust @Byron finally feels to have found the right tool for the job!
