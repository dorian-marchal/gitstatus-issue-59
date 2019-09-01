```sh
cd /tmp
git clone https://github.com/dorian-marchal/gitstatus-issue-59
cd gitstatus-issue-59

mkdir foo
touch foo/bar
touch foo/baz

. ~/gitstatus/gitstatus.plugin.sh

gitstatus_start -e -d 99

gitstatus_query

git status # Reports a new foo/ dir.
git status --untracked-files # Reports two new foo/{bar,baz} files.

echo $VCS_STATUS_NUM_UNTRACKED # 0
echo $VCS_STATUS_HAS_UNTRACKED # 0
```
