# ansible-nzbget

[![Build Status](https://travis-ci.org/mpataki/ansible-nzbget.svg?branch=master)](https://travis-ci.org/mpataki/ansible-nzbget)

This roles installs, configures, and runs [nzbget](https://nzbget.net://nzbget.net/).

## Requirements

Really this should work on any debian based system, but has been tested on a Raspberry Pi running Rasbian (stretch).

## Role Variables

These variables are largely straight out of the nzbget config file. See [nzbget.conf](templates/nzbget.conf) and the [defaults](defaults/main.yml).

## Dependencies

None.

## Example Playbook

```yml
    - hosts: pi
      roles:
        - role: mpataki.nzbget
          tags: nzbget
          vars:
            version: '20.0'
            news_servers:
              - id: 1
                name: 'newshosting'
                host: news.newshosting.com
                port: 563 # ssl
                username: <your-user-name>
                password: <your-password>
                encryption: 'yes'
                cipher: 'RC4-MD5'
            categories:
              - id: 1
                name: movies
                destination: movies
              - id: 2
                name: shows
                destination: shows
```

