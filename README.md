Heroku buildpack: Transcrypt
============================

This buildpack allows you to decrypt your [transcrypt](transcrypt)-encrypted
files on deploy.

To use this buildpack, you need to set `TRANSCRYPT_PASSWORD` and
`TRANSCRYPT_CIPHER` [config variables](config-vars) on your app.
The password is mandatory and buildpack will fail if it's missing, but
the cipher is optional and defaults to `aes-256-cbc` if not set.

This buildpack does not have any extra dependencies, except for `git` and
`openssl`, which should be available by default.

It does not use `transcrypt` script itself but calls `openssl enc` to
decrypt the files instead.


[transcrypt]: https://github.com/elasticdog/transcrypt
[config-vars]: https://devcenter.heroku.com/articles/config-vars
