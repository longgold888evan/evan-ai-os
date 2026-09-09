# Audience Targeting

Operations defines semantic audience tags. LLM converts tags into search queries. Search queries retrieve triggered items from the search index. User historical behavior is compared with triggered items to score audience relevance and output target user IDs.

Tag → LLM query generation → item retrieval → user-history relevance scoring → audience user IDs

Key evaluation question: predict relevant future behavior, not merely historical semantic similarity.
