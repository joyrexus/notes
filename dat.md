Dat: git for data

Dataset cloning: You just get the full thing and then you have it all. And then you can say tomorrow, “Give me everything since yesterday,” and you’ll just get the new stuff. 

So generally, I just kind of saw that there are all these issues around data management that we have for source code that we didn’t have for data sets.

The whole point of DataCouch was I was literally ripping off GitHub, but making it for basically spreadsheets instead of for code. So it knew, it was aware of row base changes… I was just trying to build what I thought would be an awesome set of tools for managing spreadsheets. Almost like a GitHub for Google Docs or GitHub for Google Spreadsheets.

So it’s a really cool network effect if you have a system where people can be proud of what they put into it and show it off and have a profile. And I kind of wanted that for data, and I wanted it to hook into developer tools, too.

This is exactly how package managers in programming work. It’s like, the whole point of it is that you figure out some generic functionality, that you think of and find useful, you give it a name and you publish it and other people can just use your solution. But people haven’t figured that out for data sets yet. So that’s basically the problem domain I’m working in.

track all the data in LevelDB. Say you add a .csv into DAT, or you import a .csv, and then you edit a couple of columns in Excel, and then you re-import the .csv into DAT, DAT would know the difference between the first import and the second import, and then, because it knows the difference, it can more efficiently synchronize it.

So I’ve been focused on tables; not all data is in tables, but the majority of government data is. 

So Sloan is trying to put some money into the system, so that a couple colleges can afford to have scientists that focus on the open source infrastructure and reproducibility, and not just scientists that are trying to get tenure and don’t have time to work on non-essential things.

So now I basically shifted focus of the project to, instead of solving governments’ data problems, which is what I had been been doing for Code for America, I am now focusing on academic research and collaborative science, open science and like reproducibility and all these issues.

We need to find the early adopters in academia.

I’m trying to find pilot communities right now basically.

So one would be, if you’re a researcher at a university (and) you are going to put your data set up on the university’s FTP server, why not publish your data set to our package manager, which just means having a link to the FTP server at the very least? What would be even cooler is if we could give you options like, okay, once you published your package to the repository and then linked it to your one official data source, we could do a deal with Amazon and get Amazon to donate us some number of petabytes a year to make backups of scientific data. So we could automatically download a copy of your data, put it on Amazon’s Glacier cold storage service – it won’t cost Amazon very much, makes them look good, good PR for them – and then we have a backup of this dataset in case the university goes down. Or even better, we’re investing in peer-to-peer distribution strategies like BitTorrent-style stuff, so that if your university publishes it, you can run software that basically seeds the data set, and then we kind of turn it into a sort of BitTorrent tracker, so that we can see that, oh, there’s five seeds, and maybe four other universities or people – I really want to make like a study-at-home (?) screen-saver where you’re hosting the world’s research data.

Yeah, what he did was basically write some code that makes an empty DAT database, serves it online and then starts filling it with data. So it can subscribe to some upstream, in this case he’s subscribing to npm, so every time npm changes, then he puts it in DAT, but once it’s in DAT, it’s tracked and it’s sync-able, so then I can get a clone of it.

So my goal is by the end of the year we have a package manager website. So we have an initial version up, it’s called Data Decks, and DataDecks.io is where it’s at now, and essentially, this was built by one of our team members. So this is a very early version, but for example, this is a data set on Data Decks, and this is a username. So you can click on somebody and see their profile and then you can see their data sets and you can go and view all the data sets that they’ve published, and then you can see all the versions of the data set that you can download or clone the data set.

So this is like the web front-end, right? And we want to have it so that you as an organization or an individual can create an account, upload all the data sets with DAT, push them to the website, and then, like I said, we’re not going to host data, but we’re going to make it so that you could either host it on your own server or you could click a button, put it on your Google Drive, if you exceed the limits of your Google Drive, the free one, you could buy their terabyte one for $10 a month, or you can integrate with Digital Ocean which gives you SSDs so it’s really fast to clone, and there it’s $5 for 20 gigs.

So we want to integrate with the most modern cloud services. We don’t host any data; our costs are really low. And then if it’s a data set that is for research, like if you can prove that you’re a scientist, we want to be able to do things like make free back-ups of your data on Amazon, so we’re going to work on the relationships with cloud host providers, try to donate. Google actually just donated a petabyte to climate research like two weeks ago. So there’s precedent, so we’re trying to get, we want a petabyte for science so that we can give it out to researchers on behalf of Google. Put the data on Google, but they wouldn’t have to use the clunky Google interfaces to use it, because we can make really nice, easy-to-use things.

So what I’m hoping is that we can build in-roads into the research community, get some scientists using it, probably bioinformatics – I was just learning about genomes today. I want to get different popular genomes on here so that people can download them more easily for their bioinformatics research. So by the end of the year I hope to have kind of like an active community of scientific data sharing, that’s my goal.
