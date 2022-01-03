---
description: 이석찬을 Ubuntu 서버에 설치하는 방법에 대해 다룹니다.
---

# 이석찬 설치하기

## 서버 사양 확인하기

이석찬을 사용하기 위해서는 Linux 기반의 서버가 필요합니다. 이 문서에서는 Ubuntu/Apache2를 기준으로 설명합니다.

## 아파치 설치하기

```bash
$ sudo apt install apache2
```

## Mysql 설치하기

```bash
$ sudo apt install mysql-server
```

## PHP 설치하기

이석찬은 PHP 8.0 이상 버전에서 작동합니다.

### PHP 및 아파치 PHP 모듈 설치

```bash
$ sudo apt install php8.0 libapache2-mod-php
```

### PHP 익스텐션 설치

CodeIgniter 4를 위한 PHP 익스텐션을 설치합니다. CodeIgniter 4 실행을 위한 PHP 익스텐션의 종류는 다음 링크에서 확인할 수 있습니다([https://github.com/codeigniter4/CodeIgniter4](https://github.com/codeigniter4/CodeIgniter4)).

```bash
$ sudo apt install php8.0-intl php8.0-mbstring php8.0-mysqlnd php8.0-curl
$ sudo a2enmod intl
$ sudo a2enmod mbstring
$ sudo a2enmod mysqlnd
$ sudo a2enmod curl
```

## CodeIgniter 4 설치

본 매뉴얼에서는 CodeIgniter 4를 설치하는 방법 중 Composer를 이용한 설치만을 다룹니다. 다른 설치 방법에 대해서는 CodeIgniter4 매뉴얼([https://codeigniter.com/user\_guide/index.html](https://codeigniter.com/user\_guide/index.html))의 Installation 항목을 참조하십시오.

### Composer 설치

Composer를 PHP 8.0 이상 버전에서 정상적으로 사용하기 위하여서는 Composer 2 이상의 버전을 설치하여야 합니다. 이석찬 레포지토리에는 최신 버전의 Composer를 설치하기 위한 쉘 스크립트(install\_composer.sh)가 내장되어 있습니다. 아래를 실행하여 Composer를 설치할 수 있습니다.

```bash
$ sudo sh install_composer.sh
$ sudo mv composer.phar /usr/bin/composer
```

### CodeIgniter 4 및 라이브러리 설치

Composer를 통해 CodeIgniter 4 및 이석찬 실행을 위한 기타 라이브러리를 설치합니다.

```bash
$ composer install
```

{% hint style="info" %}
`composer install` 명령어 실행 도중, 필요한 PHP 익스텐션이 설치가 되지 않아 오류가 발생할 수 있습니다. 이 경우 [PHP 익스텐션 설치](installation.md#php-1) 항목을 참고하여 누락된 익스텐션을 설치해야 합니다.
{% endhint %}

## 환경 변수 설정하기

이석찬 내부에서 사용되는 환경 변수를 설정할 수 있습니다. 환경 변수 파일은 `.env`파일이며, 레포지토리에 첨부되어 있는 `env`파일을 복사하여 생성하면 됩니다.

## 서버 시동하기

Apache 2 및 MySQL를 실행합니다.

```
$ sudo serivce apache2 start
$ sudo service mysql start
```

## 이석찬 설치하기

### 설치 관리자 접속하기

### 데이터베이스 설치하기

### 전역설정 지정하기

### 기본 계정 생성하기

