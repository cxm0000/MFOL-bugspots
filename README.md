# Bugspots - Bug Prediction Heuristic

An implementation of the simple bug prediction heuristic outlined by the Google Engineering team: [Bug Prediction at Google](http://google-engtools.blogspot.com/2011/12/bug-prediction-at-google.html)

> Well, we actually have a great, authoritative record of where code has been requiring fixes: our bug tracker and our source control commit log! The research indicates that predicting bugs from the source history works very well, so we decided to deploy it at Google.

Point bugspots at any git repo and it will identify the hotspots for you.

## Usage

```bash
$> gem install MFOL-bugspots
$> bugspots /path/to/repo -b develop -f ".php"
$> git bugspots (in root of current git project, --help for options)
```

* With the "-f" tag you could specify one file extension to go through, the default value is ".php"
* The files with very very low scores are ignored in the result list.


An example of the command could be:

```bash
bugspots /PATH/TO/REPO -b develop -f .php -r "/^bug( |-)/i"
```

This means to find all comments starting with bug(case insensitive) from the REPO
in the "develop" branch and then caculate on only php files.


### License

(MIT License) - Copyleft (c) 2015 Xiaoming Cai
