# docker-inotify-test
A small project that I'm using to test if inotify is working on a Docker Host
(Mac/Windows) or not...


## How to use:

1: Clone it and run it:

```bash
# 1. Clone it:
git clone https://github.com/vovimayhem/docker-inotify-test.git inotify-test

# 2: Start it:
cd inotify-test && docker-compose run monitor
```

2: Modify the contents of the `test_folder`, and see if the monitor tells you
something or not:

```bash
# in a separate terminal:

touch test_folder/.keep # Should read "ATTRIB .keep" on the monitor

echo $(date) >> test_folder/blah.txt # Should read "CREATE blah.txt" and then "MODIFY blah.txt" on the monitor
```
