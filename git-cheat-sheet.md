### Index
* [Kurulum](#kurulum)
* [Yapılandırma](#yapılandırma)
* [Oluşturma](#oluşturma)
* [Yerel Değişiklikler](#yerel-değişiklikler)
* [Arama](#arama)
* [Commit Geçmişi](#commit-geçmişi)
* [Branches & Tags(Etiketler)](#branches--tags)
* [Güncelleştirme & Yayınlama](#güncelleştirme--yayınlama)
* [Merge(Birleştirme) & Rebase](#merge--rebase)
* [Geri Alma](#geri-alma)

<hr>

## Kurulum

##### Mevcut ayarları göstermek:
```
$ git config --list
```
##### Repository(depo) ayarlarını göstermek:
```
$ git config --local --list
```

##### Global ayarları göstermek:
```
$ git config --global --list
```

##### Sistem ayarlarını göstermek:
```
$ git config --system --list
```

##### Sürüm geçmişinde gözükecek adı belirlemek:
```
$ git config --global user.name “[firstname lastname]”
```

##### Sürüm geçmişinde ilişkilendirilecek e-postayı belirlemek:
```
$ git config --global user.email “[valid-email]”
```

##### Otomatik komut satırı renklendirmesini ayarlamak:
```
$ git config --global color.ui auto
```

##### Commitler için global yazı editörünü ayarlamak:
```
$ git config --global core.editor vi
```

<hr>

## Yapılandırma

##### Repositorye(depoya) özgü yapılandırma dosyası [--local]:
```
<repo>/.git/config
```

##### Kullanıcıya özel yapılandırma dosyası [--global]:
```
~/.gitconfig
```

##### Sistem genelinde yapılandırma dosyası [--system]:
```
/etc/gitconfig
```

<hr>

## Oluşturma

##### Var olan bir repositoryi(depoyu) klonlama:
```
$ git clone ssh://user@domain.com/repo.git
```

##### Yeni bir yerel repository(depo) oluşturma:
```
$ git init
```

##### Belirli dizinde yerel repository(depo) oluşturma:
```
$ git init <directory>
```

<hr>

## Yerel Değişiklikler

##### Çalışılan dizindeki dosyaların değişimi:
```
$ git status
```

##### İzlenen dosyalardaki değişiklikler:
```
$ git diff
```

##### Tüm güncel değişiklikleri sonraki commite ekleme:
```
$ git add .
```

##### Sonraki commite &lt;dosyasındaki&gt; bazı değişikleri ekleme:
```
$ git add -p <file>
```

##### Tüm izlenen dosyalardaki yerel değişiklikleri Commitleme:
```
$ git commit -a
```

##### Önceden hazırlanan değişiklikleri commitleme:
```
$ git commit
```

##### Mesaj ile commitleme:
```
$ git commit -m 'message here'
```

##### Önceki belli bir tarihe commitleme:
```
git commit --date="`date --date='n day ago'`" -am "Commit Message"
```

##### Son commiti değiştirme:<br>
###### Yayınlanan commite değişiklik yapmayın!
```
$ git commit --amend
```

##### Mevcut branchteki kaydedilmemiş commitleri diğer bazı branchlere taşıma:
```
git stash
git checkout branch2
git stash pop
```

##### Saklanan değişiklikleri mevcut branche geri yükleme:
```shell
$ git stash apply
```

#### İstenilen saklanma yerini mevcut branche geri yükleme:
- *{stash_number}* `git stash list` ile elde edilebilir

```shell
$ git stash apply stash@{stash_number}
```

##### Saklanan değişiklikleri kaldırma:
```
$ git stash drop
```

<hr>

## Arama

##### Bir metni dizindeki bütün dosyalarda aramak:
```
$ git grep "Merhaba"
```

##### Bir metni herhangi bir sürüm içinde aramak:
```
$ git grep "Merhaba" v2.5
```

##### Belirli bir kelimeyi içeren commitleri göstermek:
```
$ git log -S "keyword"
```

##### Belirli bir kelimeyi içeren commitleri göstermek (düzenli ifadeler kullanarak):
```
$ git log -S "keyword" --pickaxe-regex
```

<hr>

## Commit Geçmişi

##### Tüm commitleri en yenisinden başlayarak listeler:
```
$ git log
```

##### Tüm commitleri görüntüler(Sadece commit hash ve commit mesajı görüntülenir.):
```
$ git log --oneline
```

##### Belli kullanıcıya ait commitleri görüntüler:
```
$ git log --author="username"
```

##### Belirli bir dosya üzerinde zaman içinde meydana gelen değişiklikleri göstermektedir:
```
$ git log -p <file>
```

##### &lt;Dosyayı&gt; kimin ne zaman değiştirdiğini gösterir:
```
$ git blame <file>
```

##### Referans kayıtlarını gösterir:
```
$ git reflog show
```

##### Referans kayıtlarını siler:
```
$ git reflog delete
```

<hr>

## Taşı / Yeniden Adlandır

##### Dosyayı yeniden adlandırmak:

Index.txt'den Index.html'e

```
$ git mv Index.txt Index.html
```

<hr>
## Branches & Tags

##### Tüm var olan branchleri listeler:
```
$ git branch
```

##### Ana branchi değiştirir:
```
$ git checkout <branch>
```

##### Mevcut ana branchte yeni bir branch oluşturur:
```
$ git branch <new-branch>
```

##### Remote branchte yeni bir izlenen branch oluşturur:
```
$ git branch --track <new-branch> <remote-branch>
```

##### Yerel branchi siler:
```
$ git branch -d <branch>
```

##### Güncel commiti etiket ile işaretler:
```
$ git tag <tag-name>
```

##### `HEAD`i  etiket ile işaretler ve bir mesaj eklemek için yazı editörünü açar:
```
$ git tag -a <tag-name>
```

##### `HEAD`i bir mesaj içermek şartı ile etiketler:
```
$ git tag <tag-name> -am 'message here'
```

##### Tüm etiketleri listeler:
```
$ git tag
```

##### Tüm etiketleri mesajları ile listeler (etiket mesajı yoksa bir etiket mesajı yaz):
```
$ git tag -n
```

<hr>

## Güncelleştirme & Yayınlama

##### Yapılandırılmış tüm güncel remoteları listeler:
```
$ git remote -v
```

##### Belirli bir &lt;remote&gt; hakkında bilgileri gösterir.:
```
$ git remote show <remote>
```

##### Yeni remote repository oluşturur, &lt;remote&gt; diye isimlendirir:
```
$ git remote add <remote> <url>
```

##### &lt;Remote&gt; da bulunan tüm değişiklikleri indirir, ama ana brachle birleştirmez:
```
$ git fetch <remote>
```

##### Değişiklikleri indirir ve doğrudan ana brache merge/integrate eder:
```
$ git remote pull <remote> <url>
```

##### Tüm ana Branchteki değişiklikleri yerel repositorye ekler:
```
$ git pull origin master
```

##### Remote da bulunan repositorye(depoya), yerel değişiklikleri yayınlar:
```
$ git push remote <remote> <branch>
```

##### Remote da bulunan bir branchi siler:
```
$ git push <remote> :<branch> (since Git v1.5.0)
```
ya da
```
$ git push <remote> --delete <branch> (since Git v1.7.0)
```

##### Etiketleri yayınlar:
```
$ git push --tags
```

<hr>

## Merge & Rebase

##### Seçili HEADinizi istediğiniz &lt;branch&gt;'e merge eder:
```
$ git merge <branch>
```

##### Seçili HEADinizi şimdiki &lt;branch&gt;'e rebase yapar<br>
###### Yayınlanan committen sonra rebase yapmayın!
```
$ git rebase <branch>
```

##### Rebase iptal etmek:
```
$ git rebase --abort
```

##### Çakışmaları çözümledikten sonra rebase devam etmek:
```
$ git rebase --continue
```

##### Çakışmaları çözmek için yapılandırılmış birleştirme aracını kullanmak:
```
$ git mergetool
```

##### Editörünüzü kullanarak çakışmaları çözümledikten sonra dosyayı çözümlenmiş olarak ekleyin:
```
$ git add <resolved-file>
```
```
$ git rm <resolved-file>
```

##### Commitleri birleştirmek:
```
$ git rebase -i <commit-just-before-first>
```

Bu metni,

```
pick <commit_id>
pick <commit_id2>
pick <commit_id3>
```

bu metin ile değiştirin,

```
pick <commit_id>
squash <commit_id2>
squash <commit_id3>
```

<hr>

## Geri Alma

##### Çalışılan dosyadaki tüm yerel değişiklikleri kaldırır:
```
$ git reset --hard HEAD
```

##### Evreleme alanı dışındaki tüm dosyaları alır(örnek: son git add'i geri alır):
```
$ git reset HEAD
```

##### Belli bir dosyadaki yerel değişiklikleri kaldırır:
```
$ git checkout HEAD <file>
```

##### Silinen dosyayı geri döndürme dosyanın commit loglarının tutuluyor olması ile mümkündür:
```
$ git revert <commit>
```

##### Belirlediğiniz HEADden bir önceki commite döner ve belirlemiş olduğunuz committe yaptığınız tüm değişiklikleri geri alır:
```
$ git reset --hard <commit>
```

##### Belirlediğiniz HEADden bir önceki commite döner ve belirlemiş olduğunuz committe yaptığınız tüm değişiklikleri untracked dosyalar arasına alır:
```
$ git reset <commit>
```

##### Belirlediğiniz HEADden bir önceki commite döner ve yaptığınız tüm değişiklilkleri local commitlerinizi tutarak geri alır:
```
$ git reset --keep <commit>
```


##### Gitignore'a eklenmeden önce yanlışlıkla kaydedilmiş dosyaları kaldırın:
```
$ git rm -r --cached .
$ git add .
$ git commit -m "remove xyz file"
```

