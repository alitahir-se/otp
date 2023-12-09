# OTP System

### Goal

The goal of the project is to create highly scalable and secure otp system, that can be used by any application. 

### High Level Architecture

The planned architecture is available in miro. It is at its very initial stages and will evolve overtime to include docker, kubernetes, and API gateway

https://miro.com/app/board/uXjVNEti8jc=/?share_link_id=182970526901

The decision to use API gateway is not yet final.


### OTP Delivery

The idea is to provide integration with multiple delivery channels and systems, in the delivery service. So far the planned channels are SMS, WhatsApp and Email.
For SMS and Email, multiple systems will be considered like Twilio, Amazon SNS, and OCI notification service etc.

the particular systems to use shall be configurable and the channel will depend on individual request. 
The Request will be able to include multiple channels that can either send same or different OTP for enhanced security

### OTP Generation & Verification Separation

the otp generation is separated from verification considering the difference in number of requests. 
Often, verification API needs to handle more requests because of retries and otp guessing systems. 
In case verification service faces such issues, generation will not be affected and system can mitigate the brute force attacks

Apart from that generation of otp can use complex algorithms for enhanced security, which can require more resources. 

### Security

Rate lmiting will be included at a later stage


## Commit message format

Using [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for commit messages.
To ensure that the commit messages are formatted correctly, we use [commitlint](https://commitlint.js.org/#/).
It will check the commit messages against the rules defined in [commitlint.config.js](./commitlint.config.js).
Checks are done automatically on every commit made locally and on every pull request.

**IMPORTANT**: To enable commit-lint locally you need to run `npm install` in the root of the project.

There is a [plugin](https://plugins.jetbrains.com/plugin/13389-conventional-commit) for IntelliJ IDEA that can help you with writing commit messages in the correct format.
Or you can use [commitizen](https://commitizen-tools.github.io/commitizen/) to help you write commit messages in the correct format from you terminal.


