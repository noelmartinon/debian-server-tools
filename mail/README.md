### Outlook 2013

- Root: "Inbox"
- after account setup: [delete .pst/.ost file](http://answers.microsoft.com/en-us/office/forum/office_2013_release-outlook/outlook-2013-with-imap-deleted-items-and-trash-i/9ec6e501-8e1a-45cf-bb90-cb9e2205d025)

### Email sending and receiving

- SSL?
- headers: From, from name, To, Reply-to, Return-path, SMTP "MAIL FROM:"

### Online email tests

- https://www.mail-tester.com/


### Spamassassin test

```bash
spamassassin --test-mode -D < msg.eml
# specific test, see: man spamassassin-run
spamassassin --test-mode -D dkim < msg-signed.eml
opendkim -vvv -t msg-signed.eml
```

### Bulk email

https://support.google.com/mail/answer/81126?hl=en

#### Sender ID

- http://en.wikipedia.org/wiki/Sender_ID
- http://tools.ietf.org/html/rfc4407#section-2
- PRA: Resent-Sender > Resent-From > Sender > From > ill-formed
- http://www.appmaildev.com/

#### SPF (MAIL FROM:)

- setup
- check
- monitor

#### DKIM

- setup http://www.tana.it/sw/zdkimfilter/
- check
- monitor

#### ADSP

- https://unlocktheinbox.com/resources/adsp/

#### DMARC

Specs: https://datatracker.ietf.org/doc/draft-kucherawy-dmarc-base/?include_text=1

- setup https://unlocktheinbox.com/dmarcwizard/
- check mailto:mailtest@unlocktheinbox.com
- monitor `host -t TXT <domain>`

#### Headers

- List-Unsubscribe: <URL>
- Precedence: bulk
- Return-Path:, Reply-to:, From:, To:, Subject:
- SMTP "MAIL FORM: <from@addre.ss>"

#### Content

- online version
- who (email address) is subscribed
- contact
- unsubscribe link
- HTML and plain payload