BroPlotter
===========
Jason Smith
===========

Generates visualizations from Bro logs

--Prerequisites--

Installed bro tools (bro and bro-cut at least)

--Usage--

cat http.log | broplotter.sh [charttype] [required chart options] [...]


D3 Charts
=================================================================================
forceopacity
- Displays a force directed link graph based in d3. Reads from an autogenerated CSV file.
- Requires 4 variables {source target value nodelimit}.
- source = any bro field value
- target = any bro field value
- value = any bro field value that is an integer



--D3 Chart Examples--
=========================

Generate a force-directed graph showing two way relationships between originating IP addresses and the user-agents they're using. Connectors get darker as the response_body_len become greater.
cat logs/http.log | ./broplotter.sh forceopacity id.orig_h id.resp_h response_body_len
