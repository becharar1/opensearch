# opensearch
opensearch node dashboard and logstash
this repository presents a method to open and run combined opensearch-node dashboard and logstash cluster.
This cluster can be served by filebeat systems installed on the pc
One goal here was to test the elimination of duplicates.

This can be done in opensearch by using Piped Processing Language in the dev tools as follows:
POST /_plugins/_ppl
{
  "query": "search source=logstash-logs-*| dedup message | stats count(message) "
}
