
# Задание. Инструменты Git

[Подготовка:](png/001.png)

```
git clone https://github.com/hashicorp/terraform.git
cd terraform
git fetch --all --tags
git status
```

## 1. Полный хеш и комментарий коммита `aefea`

Команда:

```
git show -s --format='%H %s' aefea
```

[Ответ:](tools/png/002.png) (Команда git show -s показывает информацию о коммите без вывода diff. Формат %H %s выводит полный хеш и комментарий коммита.)

```
aefead2207ef7e2aa5dc81a34aedf0cad4c32545 Update CHANGELOG.md
(END)
```

## 2. Какому тегу соответствует коммит 85024d3

[Команда:](tools/png/004.png)

```
git tag --points-at 85024d3
```

[Ответ:](tools/png/003.png)

```
v0.12.23
(END)
```

## 3. Сколько родителей у коммита b8d720

[Команда:](tools/png/006.png)

```
git show -s --format='%P' b8d720
```

[Ответ:](tools/png/005.png)

```
56cd7859e05c36c06b56d013b55a252d0bb7e158 9ea88f22fc6269854151c571162c5bcf958bee2b
(END)
```

## 4. Коммиты между тегами v0.12.23 и v0.12.24

Команда:

```
git log --format='%H %s' v0.12.23..v0.12.24
```

[Ответ:](tools/png/007.png)

```
33ff1c03bb960b332be3af2e333462dde88b279e v0.12.24
b14b74c4939dcab573326f4e3ee2a62e23e12f89 [Website] vmc provider links
3f235065b9347a758efadc92295b540ee0a5e26e Update CHANGELOG.md
6ae64e247b332925b872447e9ce869657281c2bf registry: Fix panic when server is unreachable
5c619ca1baf2e21a155fcdb4c264cc9e24a2a353 website: Remove links to the getting started guide's old location
06275647e2b53d97d4f0a19a0fec11f6d69820b5 Update CHANGELOG.md
d5f9411f5108260320064349b757f55c09bc4b80 command: Fix bug when using terraform login on Windows
4b6d06cc5dcb78af637bbb19c198faff37a066ed Update CHANGELOG.md
dd01a35078f040ca984cdd349f18d0b67e486c35 Update CHANGELOG.md
225466bc3e5f35baa5d07197bbc079345b77525e Cleanup after v0.12.23 release
```

## 5. Коммит, в котором была создана функция func providerSource

[Команда:](tools/png/051.png)

```
git log --reverse --format='%H %s' -S'func providerSource(' --all
```

[Ответ:](tools/png/052.png)

```
8c928e83589d90a031f811fae52a81be7153e82f main: Consult local directories as potential mirrors of providers
(END)
```
## 6. Коммиты, в которых была изменена функция globalPluginDirs

Команда:

```
git grep -n 'func globalPluginDirs('
git log --all --format='%H %s' -S'globalPluginDirs'
```

[Ответ:](tools/png/011.png)

```
7c4aeac5f30aed09c5ef3198141b033eea9912be stacks: load credentials from config file on startup (#35952)
de49677ecdbe2dd0b7ca829ca8e93a4e4d2ddd6d Run tf exec e2e tests
65c4ba736375607b6af6c035972f7f151232b6c6 Remove terraform binary
aa3a155106931ae4688df4f27de1f16279bb8647 Remove accidentally-committed binary
e8a9debd2b4942069e2bbba583fc9193a78622cf Remove accidentally-committed binary
125eb51dc40b049b38bf2ed11c32c6f594c8ef96 Remove accidentally-committed binary
e8eec68de31703513b3e96db1f073f18dbeb2bfa backport of commit 1ee5d23894a0c9448d6787e0385dbba356db8096 (#30989)
b872613d2558931eb53e6e2f9c9c1d3e7e5ebba2 Backport of Bump compatibility version to 1.3.0 for terraform core release into v1.2 (#30990)
22c121df8631c4499d070329c9aa7f5b291494e1 Bump compatibility version to 1.3.0 for terraform core release (#30988)
fcdb5d2e558b2ea5e1a63713aca2ba9848ad2ada WIP centralized plugin finder
7c7e5d8f0a6a50812e6e4db3016ebfd36fa5eaef Don't show data while input if sensitive
35a058fb3ddfae9cfee0b3893822c9a95b920f4c main: configure credentials from the CLI config file
c0b17610965450a89598da491ce9b6b5cbd6393f prevent log output during init
8364383c359a6b738a436d1b7745ccdce178df47 Push plugin discovery down into command package
```

## 7. Автор функции synchronizedWriters

Команда:

```
git log --reverse --format='%H %an <%ae> %s' -S'func synchronizedWriters' --all
```

[Ответ:](tools/png/012.png)


```
5ac311e2a91e381e2f52234668b49ba670aa0fe5 Martin Atkins <mart@degeneration.co.uk> main: synchronize writes to VT100-faker on Windows
bdfea50cc85161dea41be0fe3381fd98731ff786 James Bardin <j.bardin@gmail.com> remove unused
(END)
```
