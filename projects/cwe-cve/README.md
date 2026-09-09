# CWE / CVE Retrieval Project

Goal: given a CWE type, extract CWE metadata and observed CVEs, enrich CVEs with record data, and save structured JSON.

Key notes: parse MITRE CWE XML with namespace-aware `xml.etree.ElementTree.iterparse`; search `.//cwe:Weakness`; extract ID, Name, Description, and Observed_Examples references. Historical pitfall: namespace-free XPath returned empty results.
