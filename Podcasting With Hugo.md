Apple Podcast Requirements Documentation:
https://podcasters.apple.com/support/823-podcast-requirements
https://help.apple.com/itc/podcasts_connect/#/itcb54353390

# Advantages:
	Cost:
		Free to 10GB, $0.015/GB-month after.
		10 million requests free, $0.36/million after.
	Performance: Auto-scaling "serverless" infrastructure, CDN etc.
	Security: Minimal attack surface (static), free Web Application Firewall.

# Initial setup

## Create accounts:
	Cloudflare
		Migrate to CF for registrar...?
		Migrate DNS to CF for domain...?
		Use CF Pages URL/subdomain instead for Apple Podcast?
	Github
	Zoho??? (IF wanting free email for domain... just need CF DNS setup...)

## Clone my repo in GitHub webUI, so pulling it to local PC sets origin automatically...
My repo: https://github.com/SkippySteve/hugo-podcast

## Caching Rules
![[Pasted image 20240502061017.png]]
![[Pasted image 20240502061046.png]]
## Test Caching Rules
![[Pasted image 20240502061344.png]]
![[Pasted image 20240502061509.png]]



# Create new episodes:
```
hugo new episode/your-title-here.md
```

# Hugo uses Markdown
Markdown is a way to minimally format text. You get formatting similar to word, but the files are easily searchable outside a text editor... which is why us code nerds love it! :)
https://www.markdownguide.org/basic-syntax/
# Modify episode/your-title-here.md
Use an existing episode as a template. Copy and paste metadata such as title, data, summary etc. and change what's necessary.
### Available Episode Metadata Parameters
https://github.com/LGiki/hugo-theme-knowing-less?tab=readme-ov-file#front-matter


# Required RSS Fields:
### For Podcast:
title
	Found in hugo.toml (line 4)
description
	Found in hugo.toml (line 57)
itunes:image
	Found in hugo.toml (line 48)
language
	Found in hugo.toml (line 2)
itunes:category
	Found in hugo.toml (lines 88-97)
itunes:explict
	Found in themes/knowing-less/layouts/rss.xml (requires editing theme git repo)
### For Each Episode:
title
	Found in episode md file
enclosure
	Found in episode md file
guid
	Uses episode link if guid not specified
# Recommended Fields:
### For Podcast:
itunes:author
	Found in hugo.toml (lines 14-15)
link
	Found in hugo.toml (line 1)
### For Each Episode:
pubDate (date in our templates)
description (This is the part of our episode md file that is below the metadata up top. Underneath the second set of +++)
itunes:duration
link (created automatically)
itunes:image (in episode md file metadata)
itunes:explicit
