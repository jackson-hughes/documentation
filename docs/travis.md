# Travis CI

Travis CI is a completely free CI/CD option available with excellent integration to Github.

## Configuration

Travis CI is configured with a `.travis.yml` file in a repository root. The `.travis.yml` defines the CI test suite that will be run by Travis.

### Boilerplate `.travis.yml`

```
sudo: required
language: python
services:
- docker
before_install:
- sudo apt-get -qq update
- echo "$ANSIBLE_VAULT_PASSWORD" > ~/.ANSIBLE_VAULT_PASSWORD
env:
- ROLEFOLDER=roles/common
- ROLEFOLDER=roles/certbot
- ROLEFOLDER=roles/plex
matrix:
  allow_failures:
  - env: ROLEFOLDER=roles/plex
install:
- pip install molecule
- pip install docker
script:
- pushd $ROLEFOLDER && molecule test
notifications:
  slack:
    secure: bAjp6O1XLyxs6WgYTBrQlhIQanNSYA/cPNCeJVt8znwvLDHRbOtR2P1ZNQZTsLhiu5DNHp59+IVwMuaBt3obITXwkzzI67nVIwvlVftskEJPFYj9ImugZmQu9fUZqhO6g1RWEiDvQQ68IBiNGArwzComk0ctDq6gY6fuwq6m6UNwXvesX2mzxQ0W9Yl+g9u8TOTPwTOA9Qj5u0kh/Isg3RUxj2ypShNmgY2L+9/jn0rOO1bU7vseHrZ/mURA27FccoHbOcqoUDylUGbu57FBIUrldvQqZoAe2ZYm/f5XNRDzQvZYjrdlRXqreuUwqbhInNd043qr32QIRj6FLdSu7biSMOjdyp6HlTZtvIv8/kqNECO8PwnhC0L+5X5yzapVOm+9TQs5zzcVN7OPNY2XmxcMC97AwltrVGJwhrSwS8ZTxSpSU459tHFLtQDEJSLLzhlir5Faw/QAxYzxS/mzX7+UvkyszP9Cz0+F0UeHzCl3Xw+t1gtdcgjtgGquroPbtmGVtmi8EBzrabpoDzqHPHJXAduqEJafdRQiCQEB5/h1fOKce7rkfwJs+2bk4DYBO4X2maNignp5bqUn2ivlEhMPqKq18/3If2YLWaVexxBhHLxF4KoHi7dheF/TB7OGk22bdxlTq3+a32FQXFCA1JnT3Wo09v8dx0hd78MryOo=
```

## Further Reading

[Travis CI docs](https://docs.travis-ci.com/)