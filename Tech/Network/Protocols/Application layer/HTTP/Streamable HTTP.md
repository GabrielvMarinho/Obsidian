It's literally [[HTTP]], but the data is trasmitted in chunks, its very common on computational heavy activities like asking something to an llm or the download percentage of a load bar.

Normal [[HTTP]] returns a Content-Length attribute
Streamable [[HTTP]] no Content-Length is given