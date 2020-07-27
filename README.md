# index-to-cloudsearch
Index to cloudsearch 2013 (don't worry it's just when they started support of it this post is from 2020) in bulks of 3000 via the rest api `usage python index_cs.py file`. Only tested on Ubuntu something.something, don't see whyit wouldn't be cross platform iirc.

Anyway I've never really found any easily documented uses of the CloudSearch API. I had this script laying around and realized it might be illustrative of the REST API, which I always found a bit confusing because either (a) was completely undocumented or (b) I had to use boto as a wrappe which was always broken. This script is the horrible code I just whipped up to builk upload to AWS CloudSearch using just the REST API. Anyway, it just makes a list, then jsonifies the objects to use a pure `requests`-based solution. I guess it'd be nice if [I linked him up](https://requests.readthedocs.io/en/master/) but isn't it part of stdlib in python3? I dunno, whatever man.Then it indexes to your AWS cloudsearch index. Then repeat until you're done. Of course look through the script and put your endpoint instead of mine please.

Anyway the script is simple, it just adds  `concurrent_docs_to_index = 3000` to a list and uses the AWS CloudSearch rest API to bulk upload them, YMMV depending on your docs, how big they are and such. Also note: I had to add my IP address in the Allow Config and that takes 10 minutes to update for some reason. I recommend not sitting there waiting if "it's done yet" and refreshing the page, but instead go grab yourself a water or a beer or something and relax somewhere.

Also, yup, it's where https://scylla.sh data lives believe it or not. Feel free to query it directly :).

# Features:

1. If you stop and start it'll continue where it left off in a file. I'm not sure if it cleans up after itself though, so just be wary of that.
2. So yeah, let's be honest, this code sucks. I should've spread it out into nice neat litle funtions etc, but I didn't really care :). To any future employers: I'm sorry, it's not usually like this!
3. I think it works on Linux and Windows? Untested but I don't see why it wouldn't work

