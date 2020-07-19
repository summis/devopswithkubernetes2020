I used [this app](https://github.com/summis/rust-string-outputter).

Created docker image with
```console
docker build -t summila/rust-string-outputter .
```
```console
docker push summila/rust-string-outputter
```

Got is up with.
```console
kubectl create deployment rust-string-outputter-dep --image=summila/rust-string-outputter
```
and view logs with
```console
kubectl logs -f rust-string-outputter-dep-5db6f95fbc-pxhlt
2020-06-14 15:28:20.059629383 UTC 5rTAyB84iFKleU9nFRJeOR3Tgdkjaq
2020-06-14 15:28:25.059791378 UTC 5rTAyB84iFKleU9nFRJeOR3Tgdkjaq
2020-06-14 15:28:30.059982080 UTC 5rTAyB84iFKleU9nFRJeOR3Tgdkjaq
2020-06-14 15:28:35.060138423 UTC 5rTAyB84iFKleU9nFRJeOR3Tgdkjaq
```
