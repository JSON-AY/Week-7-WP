# Project 7 - WordPress Pentesting

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Admin Password Brute Force
  - [ ] Summary: Used WPScan and wordlist to brute force admin account password. 
    - Vulnerability types: Weak password
    - Tested in version: 4.2
    - Fixed in version: n/a
  - [ ] GIF Walkthrough: [Imgur Link](https://imgur.com/a/GLKfJ6L)
  - [ ] Steps to recreate: 
  - Ran the following script:("wpscan --url http://wpdistillery.vm --wordlist ~/rockyo.txt --username admin")
  - [ ] Affected source code: n/a
    - [Word Press Brute Force](https://www.wpwhitesecurity.com/strong-wordpress-passwords-wpscan/)
2. Large File Upload Error XSS
  - [ ] Summary: This attack is acheived by uploading a 20Mb or larger file with the name of it reflecting a XSS prompt.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.15
  - [ ] GIF Walkthrough: [Imgur Link] (https://imgur.com/a/Z6RKAGC)
  - [ ] Steps to recreate: 
  - Downloaded a large photo file (23Mb). 
  - Renamed the file to (Dinosaurs secret life<img src=x onerror=alert(200)>.png) 
  - Dragged file into following page (http://wpdistillery.vm/wp-admin/media-new.php) 
  - XSS pop-up occurs
  - [ ] Affected source code:
    - [hackerone link](https://hackerone.com/reports/203515)
3. WordPress Stored XSS
  - [ ] Summary: Individuals includes XSS string when making a post as either a contributor or editor. When user moves mouse over the link, they're prompted with an XSS dialog pop-up. 
    - Vulnerability types:
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: [Imgur Link] (https://imgur.com/a/ltvHWbh)
  - [ ] Steps to recreate: 
  - Make post as author or contributor
  - Include the following string in the post (<a href="</a><a title=" onmouseover=alert('test')  ">link</a>))
  - When user places their cursor over the link, they're prompted with a pop up XSS dialog.
  - [ ] Affected source code:
    - [klikki Oy](https://klikki.fi/adv/wordpress3.html)
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
