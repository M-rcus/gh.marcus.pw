# Anonymity "Guide"

Last updated: 2020-07-18 (UTC)

## Disclaimer

**I am definitely no expert on the subject, but I believe I know my a decent amount about it.**  
**With that said, I am still an 'amateur', so please take this guide with a grain of salt as it's biased towards my own experiences and knowledge.**

**I advise you to research further using your favorite search engine to learn more from various other authors, especially if you wanna be as anonymous as possible.**

## Table of Contents

- [Anonymity "Guide"](#anonymity-guide)
  - [Disclaimer](#disclaimer)
  - [Table of Contents](#table-of-contents)
  - [Preface](#preface)
    - [1. Online: Virtual Private Network (VPN)](#1-online-virtual-private-network-vpn)
      - [My personal VPN recommendations:](#my-personal-vpn-recommendations)
      - [Alternative: The Tor Network](#alternative-the-tor-network)
    - [2. Payments: Use Visa/MasterCard gift cards](#2-payments-use-visamastercard-gift-cards)
    - [3. Payments: Cryptocurrencies](#3-payments-cryptocurrencies)
    - [4. Computer: Virtual Machine (VM)](#4-computer-virtual-machine-vm)
    - [5. Accounts & Social Media: Separate _ALL_ your online accounts and create a separate identity.](#5-accounts--social-media-separate-all-your-online-accounts-and-create-a-separate-identity)
    - [6. SMS: Burner phone numbers](#6-sms-burner-phone-numbers)
    - [7. Web Browser: Mozilla Firefox with Extensions](#7-web-browser-mozilla-firefox-with-extensions)
    - [8. Security: Password managers](#8-security-password-managers)
      - [Cloud based password managers](#cloud-based-password-managers)
      - [Local-file password managers](#local-file-password-managers)
    - [9. Torrents: Seedboxes](#9-torrents-seedboxes)
    - [10. Security: Two Factor Authentication (2FA)](#10-security-two-factor-authentication-2fa)
      - [Android apps](#android-apps)
      - [Desktop](#desktop)
      - [Final note about 2FA](#final-note-about-2fa)
    - [11. Accounts & Social Media: Throwaway Emails & Accounts](#11-accounts--social-media-throwaway-emails--accounts)

## Preface

This guide is meant for those of you that like to share _totally legitimate_ content, but still want to make sure to stay as anonymous as possible.

With that said, you have to draw the line somewhere and at some point. Whether you follow all my suggestions, or none of them, is ultimately up to you.

And as mentioned in the [Disclaimer](#disclaimer), I'm by far no expert on privacy stuff, but most definitely not a newbie. I am also slightly biased towards certain services as I personally use them.

I also expect you to have a reasonable amount of money to spend on certain services. We're not talking ridiculous amounts here, at least not for most of the people living in first-world countries, but it's a decent chunk of money.  
A general rule of thumb in regards to privacy: If a product is free, you are (your personal information is) the payment.  
That's not to say that every service sells your data, but a good majority do.

This guide is also heavily based on my current setup. At the end I'll list most of the software and technical stuff I use specifically.

I also want to give a shoutout to [PrivacyTools.io](https://www.privacytools.io/).

The guide will be split up into multiple chapters, in no particular order. Feedback is appreciated.  
Anyways, here we go.

### 1. Online: Virtual Private Network (VPN)

One of the most important aspects of staying anonymous in my opinion, is to use a VPN.  
A VPN essentially routes all your internet traffic to a third-party server, before going to whatever websites or service you normally visit.  
The benefit is that you can hide your real IP address from those websites or services. Most VPN providers also allow you to select what server and country you wanna connect to, allowing you to further obfuscate your location.  

Overall it doesn't really matter what VPN you use in my opinion, but some VPN services are "shadier" than others. Personally I stay away from those that have aggressive marketing with cheap prices (*cough* NordVPN, ExpressVPN - to name a few *cough*).

On Linux, I use services that support [OpenVPN](https://openvpn.net/community-downloads/) and the software [Qomui](https://github.com/corrad1nho/qomui) for managing my VPN connections. Qomui uses OpenVPN under the hood.  
Useful features is having favorite VPN servers (which I often switch between) and the **VPN killswitch** (all connections are blocked, UNLESS they go through the VPN, preventing accidental leaks of your true IP address).

#### My personal VPN recommendations:

- [Mullvad](https://mullvad.net/) / [Mozilla VPN](https://vpn.mozilla.org/)
    - The reason these are listed together is that Mozilla has partnered with Mullvad for their VPN service.
    - Supports OpenVPN and WireGuard (a different type of VPN technology).
    - Mullvad also has their own client that supports a killswitch as well.
- [ProtonVPN](https://protonvpn.com/)
    - ProtonVPN has a free plan as well, but I've only used their paid plans, so I don't know how good that is.
    - Supports OpenVPN.
- As with literally everything I list in this guide: Please do your own research.

#### Alternative: The Tor Network

While the Tor Network is better to use for anonymity and privacy reasons, a lot of services have blocked Tor exit nodes.  
Google ReCaptcha is also really aggressive against Tor (this is an issue with VPNs too, but not to the same extent), making it really annoying to deal with.  
Using Tor might be beneficial in some cases, so I'm mentioning it here, but I personally don't rely on it too much due to my VPN setup. Of course it's somewhat stupid to put "all my eggs in one basket", so once again; do your own research. :)

> [Tor Project](https://www.torproject.org/)

### 2. Payments: Use Visa/MasterCard gift cards

A lot of countries have Visa/MasterCard gift cards that work practically the same as normal debit or credit cards.  
With that said, not all services support you paying with them, but I'd say about 90% do.

Ideally you'd get 2 or 3 refillable cards, which gives you three benefits:

- You can cycle through cards
- If one gets "burned" (can no longer be used) on Onlyfans, Patreon or whatever, you can use one of the other ones.
- Since they're refillable, you don't need to add a new card once your old ones get empty. Just add more money to it.

You'd have to do your own research as to what type of gift cards like these exist in your country (if any) as I don't know of any "master lists". Some countries have refillable ones, while others have only "one-time fill use" (you can fill it once, but once credit is used, it's useless).

### 3. Payments: Cryptocurrencies

I was kind of hesitant to include this little point in my guide, but it's worth mentioning at least. Cryptocurrencies are essentially: "a bit tedious to use, but gives a little bit more privacy if used correctly".  
A lot of services DON'T support these and even if they do, it's usually just Bitcoin (maybe Ethereum).  
They're generally 'slow' (transactions take a while to go through), but relatively "safe" to use (at least in my usecases).

Cryptocurrencies are not useful for paid sites like Onlyfans or Patreon, but if you're planning on getting a seedbox for torrents ([chapter #9][CH-9]), then a good chunk of seedbox providers support cryptocurrencies.

I'll be honest, I don't really know if I wanna talk about them more. I actually try to use them as little as possible, because they're pretty annoying to deal with IMO, but hey. Read more up on it if you want :^)

### 4. Computer: Virtual Machine (VM)

A Virtual Machine (or a VM) is practically speaking a separate operating system that runs on the same computer, in an isolated environment. It allows you to install another instance of Windows or Linux and run it separate from the main operating system.  
You will still use the same computer, but you'll practically have a "window" into a separate operating system that doesn't directly affect your main computer (besides usage of hardware like CPU, RAM, storage etc.).

I personally run a Linux distribution (Xubuntu 18.04 as of right now), with a VPN killswitch (as mentioned in [chapter #1][CH-1]), but honestly any OS or distribution would work.  
My Linux distribution isn't setup with anything in particular, other than the fact that I'm using a separate identity (username), in case my system gets compromised somehow.

If you plan on trying out Linux as well, then any [flavor of Ubuntu](https://wiki.ubuntu.com/UbuntuFlavors) is generally safe to start off with.  
With that said, running Linux might not be the best idea unless you're already familiar with it. It can be a pain in the ass to deal with when it comes to being a desktop OS, but it's not the worst thing in the world.  
You might not enjoy it all that much if you don't like tinkering and troubleshooting tech.

### 5. Accounts & Social Media: Separate _ALL_ your online accounts and create a separate identity.

This is probably the most important part and having it as #5 is kind of dumb, but fuck it.  
Everything else is pointless if you decided to connect your personal Facebook account to your Discord account. At that point you've practically doxxed yourself. Dumbass.  

Start with a fresh email address. I recommend using [ProtonMail](https://protonmail.com/) or [Tutanota](https://tutanota.com/). They're both privacy-oriented email services.  

Make sure to only create social media accounts that you 'require'. If you need a phone number for certain social media to unrestrict your account, see [chapter #6][CH-6].

If you're planning on leaking content from multiple creators, it's probably a good idea to also use separate Onlyfans accounts for those.  
I personally rotate between 2-3 accounts, but I am subbed to multiple creators on each one (imo one account per creator is overkill).  
This is also where "refillable cards" ([chapter #2][CH-2]) are handy.

### 6. SMS: Burner phone numbers

This would allow you to "verify" your social media accounts without using your own phone number. The only service I can recommend here is [Crypton.sh](https://crypton.sh/) to be honest, which costs 8 EUR per month (per phone number).

This seems like a damn advertisement, but I just don't know of any other services that fit the criteria.  
And do I really need to explain why tying your personal phone number to burner accounts is a bad idea? I sure hope not.

### 7. Web Browser: Mozilla Firefox with Extensions

Practically every website and service tracks you somehow, especially social media services and that's probably not news to many people.  
To prevent as much tracking as possible, I suggest you follow [PrivacyTools.io's browser guide](https://www.privacytools.io/browsers/#browser).  
While you don't have to do everything (some of the [configuration options](https://www.privacytools.io/browsers/#about_config) might break various sites), it's a good idea to do at least some of it.

My suggestion is to at least make use of [the addons](https://www.privacytools.io/browsers/#addons), such as [Ublock Origin](https://addons.mozilla.org/firefox/addon/ublock-origin/) which blocks both ads and trackers, as well as make use of [Firefox's container feature](https://support.mozilla.org/kb/containers).

### 8. Security: Password managers

A password manager is a must-have in any aspect in my opinion. Which one you use generally doesn't matter, at least if you stick to the big names.  
Using a password manager will allow you to not only keep track of what sites and services you have an account on, it's also much easier to create passwords that are complex and won't be bruteforced (even though that's unlikely in this day and age).

The idea of a password manager is that you create an entry for every account and you generate a random password for each account.

One thing you'll have to consider is convenience vs. security. Know your threat model and _do your own research_.

#### Cloud based password managers

- [Bitwarden](https://bitwarden.com/) - My personal recommendation.
    - I host my own server of Bitwarden using [bitwarden_rs](https://github.com/dani-garcia/bitwarden_rs).
    - The "official" version has a free plan that works just as good, though the paid plan is only $10 per year anyways.
- [1Password](https://1password.com/)
    - Not much experience with this, but it's recommended by people like [Troy Hunt](https://twitter.com/troyhunt) - The creator of [HaveIBeenPwned](https://haveibeenpwned.com/).
- [LastPass](https://www.lastpass.com/) - Honorable mention.

#### Local-file password managers

By "local" I mean that the databases are saved into a local file, instead of an external service.  
It's very much possible to use a local password manager and sync it to other devices, using a cloud service like Google Drive, Dropbox, Nextcloud, Mega etc.

The only local password managers that I am familiar with are _variants_ of [KeePass](https://keepass.info/). KeePass is the "OG version", but there are other implementations and variants such as [KeePassXC](https://keepassxc.org/) and [KeeWeb](https://keeweb.info/).

PrivacyTools.io has a ["Worth mentioning" section on their password managers page](https://www.privacytools.io/software/passwords/) that lists others as well.

### 9. Torrents: Seedboxes

This is kind of niche as most people might not need to care about this, but if you're planning on doing anything with torrenting, I highly recommend getting a seedbox.

I personally use [Feral Hosting](https://www.feralhosting.com/) due to their "unlimited bandwidth" (which is helpful for seeding public torrents that use a lot of bandwidth).

Other honorable mentions, that also support public trackers (though some have limited bandwidth, so keep that in mind):

- [SeedHost](https://www.seedhost.eu/)
- [Seedboxes.cc](https://seedboxes.cc/)
- [PulsedMedia](https://pulsedmedia.com/)

### 10. Security: Two Factor Authentication (2FA)

This is a recommendation for your "normal" personal accounts as well. Use 2FA everywhere. Preferably the Time-based One-Time Password (TOTP) variants.  
TOTP is often advertised as "Google Authenticator". It's [a standard that most sites should implement](https://en.wikipedia.org/wiki/Time-based_One-time_Password_algorithm), but some are lazy and use services like Authy instead (*cough* Twitch *cough*).  

While Authy is not a bad app by any means, it requires you to tie your phone number to it and... well, I don't need to tell you why that might be a bad idea.

2FA is _less necessary_ when you're using a password manager, as the chance of someone getting into your account with a randomly generated password is near-zero.  
With that said, I would still recommend you utilize 2FA wherever you can.

Also, make sure to _backup_ your 2FA codes frequently. The apps I recommend should have that ability.

#### Android apps

- [andOTP](https://github.com/andOTP/andOTP#andotp----android-otp-authenticator)
- [Aegis](https://getaegis.app/)

#### Desktop

I don't personally know of any 2FA apps for "desktop" usage, besides using your password manager. I know Bitwarden supports it at least.  

**Note:** I do not recommend saving your 2FA token in your password manager, as that pretty much ruins the whole point of 2FA.  
With that said, it is an option and worth mentioning.

#### Final note about 2FA

If you create a lot of throwaway accounts, obviously there's no need to add 2FA on every single one. They're "throwaway" for a reason.

### 11. Accounts & Social Media: Throwaway Emails & Accounts

I don't use throwaway emails very often, unless it's for spam services or whatever.  
One thing I do use them for is for creating tons of Mega accounts to leak things on, since they often get DMCA'd anyways.

There are a ton of providers for temporary emails, I'm not gonna bother listing all of them. Just search for something like "throwaway email" and you'll be good to go.

**Note**: I don't recommend using these kind of throwaway emails for more 'permanent' accounts, that's where [chapter #5][CH-5] is handy :)

- [SharkLasers / GuerillaMail](https://www.sharklasers.com/)
- [Temp Mail](https://temp-mail.org/en/)
- [10 Minute Mail](https://10minutemail.com/)


[CH-1]: #1-online-virtual-private-network-vpn
[CH-2]: #2-payments-use-visamastercard-gift-cards
[CH-3]: #3-payments-cryptocurrencies
[CH-4]: #4-computer-virtual-machine-vm
[CH-5]: #5-accounts--social-media-separate-all-your-online-accounts-and-create-a-separate-identity
[CH-6]: #6-sms-burner-phone-numbers
[CH-7]: #7-web-browser-mozilla-firefox-with-extensions
[CH-8]: #8-security-password-managers
[CH-9]: #9-torrents-seedboxes
[CH-10]: #10-security-two-factor-authentication-2fa
[CH-11]: #11-accounts--social-media-throwaway-emails--accounts