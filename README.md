# index-to-cloudsearch
Index to cloudsearch via the rest api

I've never really found any easily documented uses of the CloudSearch API. I had this script laying around and realized it might be illustrative of the REST API. By the way tup, it's where scylla.sh data lives believe it or not. Feel free to query it directly even! Note for this to work you have to 

# Features:

1. If you stop and start it'll continue where it left off in a file. I'm not sure if it cleans up after itself though, so just be wary of that.
2. So yeah, let's be honest, this code sucks. I should've spread it out into nice neat litle funtions etc, but I didn't really care :). To any future employers: I'm sorry, it's not usually like this!
3. I think it works on Linux and Windows? Untested but I don't see why it wouldn't work

Anyway the script is simple, it just adds  `concurrent_docs_to_index = 3000` to a list and uses the AWS CloudSearch rest API to bulk upload them, YMMV depending on your docs and stuff. Also note: I had to add my IP address in the Allow Config).
