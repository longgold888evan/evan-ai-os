# Audience Targeting

Goal: build an audience targeting system from semantic operator tags to target user IDs.

Architecture: Tag → LLM-generated search queries → search index items → compare against user historical behavior → audience relevance score → user IDs.

Key concern: define and validate relevance using future behavior, not just historical overlap.
